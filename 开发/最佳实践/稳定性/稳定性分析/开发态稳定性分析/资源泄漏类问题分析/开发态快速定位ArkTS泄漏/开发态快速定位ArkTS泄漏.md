# 开发态快速定位ArkTS泄漏

更新时间：2026-09-09 06:06:31

来源：https://developer.huawei.com/consumer/cn/doc/best-practices/bpta-arkts-leak-in-develop

## 概述

在ArkTS中，开发者无需手动管理内存。但如果代码中存在不合理的引用，则会导致内存无法被正确回收，从而引发内存泄漏。本文将通过常见泄漏场景和ArkTS内存泄漏分析案例，帮助开发者快速定位应用中的内存泄漏问题。
 
 

## ArkTS内存泄漏根因

ArkTS运行时采用[HPP GC](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/gc-introduction#hpp-gc)（即高性能部分垃圾回收），将对象按生命周期划分为新生代和老年代。使用标记-清除（mark-and-sweep）算法回收内存，可达对象被标记为存活，其余对象将被回收。，GC从根节点开始遍历，根节点因此被称为[GC Root](#table17319174010236)。该树的快照如下图所示。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/da/v3/UHizxGGVRKuVAY8iQoRAiQ/zh-cn_image_0000002675100549.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=01C46A184E804AC2D5F2C1635E7C22F39F30EFB95C56C1F7F1F5997EA08685AD)

 
理解垃圾回收（GC）机制的核心，在于把握一个根本原则：GC仅回收那些从GC Root不可达的对象。换言之，只要一个对象仍处于引用树的路径之上，即便它已被程序逻辑遗忘、不再被实际需要，GC也无力将其回收。内存泄漏的本质不是GC失效，而是开发者留下了不该留的引用链。因此排查内存泄漏的关键，就是找到那条从GC Root出发、让无用对象“存活”的引用路径，并在适当位置将其切断。
 
 

## 常见泄漏场景

 

### JS对象被VMRoot类型持有导致内存泄漏

常见构成[VMRoot](#table17319174010236)引用的来源包括：
 
- 模块导出对象：export出的对象被底层的SourceTextModule系统对象持有，而模块本身在应用生命周期内不被卸载。
- 全局对象属性：通过globalThis.xxx = ... 挂载的对象，globalThis是贯穿应用始终的根对象。
- 内置原型链扩展：修改Array.prototype、Object.prototype等内置对象原型，导致意外全局持有。

 
一旦业务对象挂载到上述根节点上，即使页面销毁、组件卸载，该对象依然被VMRoot强引用，GC无法回收。
 
 

### JS对象被Local Handle/Global Handle引用导致内存泄漏

 
在鸿蒙的JS-Native交互中，JS对象可以通过NAPI Native代码访问或持有。Native代码为了引用这些JS对象，会使用两种主要的句柄类型：napi_value、napi_ref。其中，napi_ref是一种引用计数的句柄，用于保持对JS对象的引用，防止其在Native代码持有引用期间被垃圾回收器回收。
 
- Local Handle (napi_value): 通常指在Native代码执行上下文中创建的、作用域较短的引用。当Native代码执行环境切换时，这些[Local Handle](#table17319174010236)通常会被自动清理。Local Handle受Handle Scope管理，大部分场景下（如同步调用、napi框架异步调用等）系统会为创建的Local Handle添加Handle Scope，但仍有部分场景（如libuv异步调用等）系统不会主动添加Handle Scope，需要应用自行管理，否则就会导致JS对象无法回收。
- Global Handle (napi_ref): 这是一种作用域为整个应用生命周期的引用。一旦创建，除非显式删除，否则它会一直保持对JS对象的引用。通常用于需要跨模块、跨上下文甚至跨JS线程访问的JS对象。由于其持久性，如果不加注意，很容易成为JS对象泄漏的根源。

 
当Native代码持有（无论是local还是global）一个JS对象时，它实际上建立了一种强引用关系。在JS引擎的垃圾回收机制中，如果一个JS对象的所有可达性引用（包括JS代码内部的引用、DOM树等）都被清除，该对象就可以被回收。然而，如果存在一个Native句柄指向它，那么这个句柄就构成了一个阻止根，使得该JS对象在Native代码持有该句柄期间，从垃圾回收器的角度看，它是“可达”的。这就阻止了JS对象被回收，从而可能导致内存泄漏。
 

### JS对象被FrameRoot类型持有导致内存泄漏

正常情况下，函数执行完毕退栈后，栈帧销毁，这些临时引用自动失效，内存随之释放。
 
然而，若函数长期不退栈，局部变量/参数所引用的对象将持续被[FrameRoot](#table17319174010236)锚定，即便业务逻辑已不再需要它们，GC也无法回收。常见导致栈帧滞留的情形包括：
 
- 死循环或无限递归，函数永不返回。
- 在函数内启动了一个长期运行的同步阻塞操作（如同步网络请求、大文件同步读写）。
- 函数内部创建了闭包并被外部长期持有，且闭包捕获了该函数栈帧中的变量（导致整个栈帧无法释放）。
- 使用了生成器（Generator）或async/await但未正确消费，导致协程挂起，栈帧保留。

 
 

## 标准化排查流程
1. 复现与观察：使用DevEco Profiler的Realtime Monitor(Memory泳道)，重复多次进出目标页面，观察内存曲线是否呈阶梯状上升。
2. 识别泄漏点：在操作前后各采集一次堆快照，使用Snapshot对比功能，关注新增对象数量和Shallow Size，从而识别泄漏点。
3. 查看对象引用链：在Snapshot快照的对象引用链中找到异常存活对象（如本该销毁的Component实例），通过“Shortest Paths”分析引用链情况。
4. 是否VMRoot持有：若引用链顶端为[VMRoot](#table17319174010236)/SourceTextModule，多为模块导出单例或全局变量未清理。
5. 是否Local/Global Handle持有：若泄漏对象的Distance为1，则多为Native侧持有未释放导致。可分为2种场景：
- [Local Handle](#table17319174010236)：napi_value未使用napi_open_handle_scope 或未成对使用（即使用napi_open_handle_scope但是未使用napi_close_handle_scope 释放）。

6. [Global Handle](#table17319174010236)：napi_ref 未调用 napi_delete_reference 释放或未成对使用（即使用napi_create_reference但是未使用napi_delete_reference 释放）在这2种情况下，无法基于引用链分析，需要通过Allocation模板，开启Local Handle及Global Handle录制选项来进一步分析。

7. 是否 FrameRoot 持有：若非VMRoot和Local Handle/Global Handle持有，则多为函数不退栈或闭包捕获对象被外部持有。

8. 代码审查：根据引用链中的关键节点（如 EventHub、Timer、全局变量、napi_ref、闭包上下文）定位代码中的持有关系。

9. 修复与验证：修改代码后重复步骤 1~2，确认内存曲线回归平稳。

  标准化排查流程整体流程如下图所示：

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/3/v3/BnoYRo6dSE6bc7VsYeaUNA/zh-cn_image_0000002675020693.jpg?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=857FB25E4A0F0DB81BCB2AA0F631EE7B1A676DB9951C4AC208F697CD7C34B4E3)


  

  ## ArkTS内存泄漏分析案例

  

  ### 案例背景

  **现象**：本案例中，通过复现“首页至消息页”的反复进出操作，观察到应用内存占用呈现“阶梯式持续增长”趋势。在循环操作10次后，应用出现显著卡顿现象。

  **初步判断**：典型的“阶梯式内存增长”，高度疑似内存泄漏。

  

  ### 分析流程

1. **Memory泳道确认泄漏**

  
打开 DevEco Studio，连接真机，点击Profiler工具Realtime Monitor（也可使用snapshot模板的Memory录制观察，以下是使用Realtime Monitor观察）。

2. 启动应用，选择设备与应用进程。

3. 点击录制按钮，在设备上重复操作：进入消息页面 → 停留2秒 → 返回首页，重复多次。

4. 观察内存曲线：
**正常预期**：每次退出后内存回落至基线附近，整体呈锯齿状。

5. **实际现象**：曲线呈阶梯状上升，多次操作后内存增长至314.1MB且无明显回落，存在内存泄漏。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d0/v3/ORiGTrWUQ56B7TzfGmj6_g/zh-cn_image_0000002645100746.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=54BE8A5EAA217E4961F9AF6DF01671671E052F17156FA68266624A1ADA0704AD)

- **堆快照对比定位异常对象**

  在 Profiler 中切换到Snapshot模板，请参考[Snapshot模板基本操作](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-snapshot-basic-operations)：选择Profiler工具 → 选择设备与应用进程 → 选择Snapshot模板 → 创建Session → 启动录制。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/c4/v3/emNJz5qAQUK9zCOOdkkp3A/zh-cn_image_0000002644940842.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=A03FD555D3F6602A5BFE703ED94CB4C22F0354DEA0A6AE2F61BAB63C27251C76)


  抓取快照1：首次在进入消息页前，点击“Take Heap Snapshot”。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/79/v3/FFslF0kMQPewcvUrwjpBcQ/zh-cn_image_0000002675100551.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=951276F86802CDF5B7526BECF800F78265E215BADDD09A6F7AAE600D4DAECB4E)


  抓取快照2：重复进出消息页面7次后，回到首页，点击“Take Heap Snapshot”，再抓取第二次快照，并停止录制。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/9b/v3/fcnWiZdnTxiOvaTr-YBI3g/zh-cn_image_0000002675020695.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=CB8D46F2EAA3EA56CFEA4C48497F76AD57B2D90FEBE888292C1A116DABBDCF8B)


  在快照对比视图Comparison中，选择CompareTo Snapshot1。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/36/v3/RRG9YbOKShymvevleHLMJw/zh-cn_image_0000002645100748.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=7FB4E06968B0B3CA21D7AAB3D933635718AA312466676E33FD45D6808479B77C)


  查看对象新增销毁情况，优先关注：

  操作次数的整数倍或整数倍+1（因为export出的对象本身也有一条引用链），

  业务对象，即Constructor的结构为包名/模块名/文件路径#泄漏对象。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/34/v3/kQsPPczUTwy6_97mFfkC6Q/zh-cn_image_0000002644940844.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=C5B253CCE1FC01DECD0C3E145EB27E6673CCD78646EAE28C11DB89174A537677)


  关键发现：

  
对比结果中，Test对象实例数量从0个增加到8个，Test对象实例泄漏。
- 正常情况下，页面退出后组件实例应被回收，快照2中应只有1个Test 对象（被export持有）。

 

- **追踪引用链**

  在快照对比视图中，展开并选中一个Test对象实例，优先选Distance数量较多的，此处我们选“6”的，并打开右侧详细信息面板。

  注：选择Distance数量较多的对象实例，主要是因为这些实例频繁地被创建且未能得到及时释放。这表明存在潜在的内存泄漏问题，需要进一步调查以确定具体的泄漏源。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/bc/v3/M5JIob53TIS9ExqLrgW1UA/zh-cn_image_0000002675100553.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=EAD022F652B9EDD73FF364831939F07CCF0B5758F18145A641357D91BE586AB8)


  点击“Shortest Paths”获得如下Test对象实例的最短引用链：

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/86/v3/g8cNLtmuTJGmgQ48lNOkEw/zh-cn_image_0000002675020697.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=78EBA7D118870A1F8D363F3ECF46D9AD71A64C14B1BAAB5B111F753D7CE6B932)

- **分析VMRoot类型持有导致泄漏问题**

1. 根据步骤3得到的Test对象实例的最短引用链分析，该引用链的GC Root为SourceTextModule符合被export模块导出对象持有，[VMRoot](#table17319174010236)泄漏场景。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/b4/v3/MpG9jHFtSpm9ysrtoy-dtA/zh-cn_image_0000002645100750.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=A2DEB10E13DA4F63BDEEFD0C99775A752BC155E2490566CEC6CF0CCE66844131)


2. 从GC Root向上排查引用链，找到第一个业务对象，即CacheTest.ts文件中的CacheTest对象的cache属性持有了Test对象未释放。点击后面跳转图标，打开CacheTest对象实例详细面板。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/62/v3/1yAfmOS-RIuMfQYCZkUrzA/zh-cn_image_0000002644940846.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=B118865B633E76555E14007C70ABE3711F4ECC2B412E8F9DAF63E93829421143)


3. CacheTest对象实例面板中，点击对象名后跳转按钮，跳转对应代码行。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/60/v3/n59D4tj8RM-ROTxATyIKLw/zh-cn_image_0000002675100555.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=DFB2DBCEFF04FDF34DDDAB427FA06CA75701F558333E24CB615190697F75DA98)


4. 跳转代码后分析，CacheTest对象存在静态属性cache，该静态属性中保存了Test对象。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/51/v3/L4kkhn_yQs6ZPdNew8NVBQ/zh-cn_image_0000002675020701.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=0BD580D3AB6000989126A600E44AA8BB81A5E90312F3D3E81142690393CFEF47)


5. 结合业务代码分析，MessageCenterPage组件创建时会保存一个Test对象到CacheTest中，但组件销毁时未清理该缓存导致内存泄漏。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/b5/v3/Jn_pxYqhQE-nz3G9u28VdQ/zh-cn_image_0000002645100752.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=444B2A9CB31977BA2EE60154C25C809473179444D23000D2911AE2691B980988)


6. 修改代码，在页面销毁时清除缓存。修改后重新复现操作7次，并抓快照验证，Test对象创建数量正常。但分析发现Proxy对象数量异常，创建70个未销毁。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ab/v3/JJQFK48WSTyyYQtU594ifA/zh-cn_image_0000002644940848.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=49C3B6BF95AA4E6830A345FC2EA7600B532144B3030388C588F49F0F57EFFAD4)


7. 参考“步骤3：追踪引用链”，找到最短引用链，发现该Proxy对象的Distance为1。说明其为GC Root直接持有的对象，被Native侧直接持有未释放，即JS对象被Local Handle/Global Handle引用导致内存泄漏。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/cd/v3/4SIy-AYBQWCO8BU_-HG2lA/zh-cn_image_0000002675100557.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=DAAAC7E216701AF1552A7DE19217511F00959546F92620B04E2AB3D67363E206)


8. 通过Proxy对象的Distance为1的References，确认内存泄漏是由JS对象被Global Handle引用导致的。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/2e/v3/2kXUeK8OQoK2zD0hBnamuQ/zh-cn_image_0000002675020703.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=1DDBD120C8358FDBF52768A722AFAE9146D9D905A2457184037BDD315BE59DD7)

- 分析Local Handle/Global Handle类型持有导致泄漏问题

  基于步骤4分析，Proxy对象实例可能被[Local Handle](#table17319174010236)/[Global Handle](#table17319174010236)引用导致内存泄漏，可通过以下步骤继续分析定位：

1. 配置Allocation录制模板并捕获数据

  
打开DevEco Studio：确保你的工程已加载，并连接了目标设备或模拟器。
- 进入Profiler模块：在主界面下方菜单栏，找到并点击Profiler选项卡。
- 选择应用进程：运行应用，并在“区域2”选择目标设备和应用进程。
- 创建Allocation录制模板：选择“Allocation”并点击Create Session创建录制模板。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/71/v3/ta_Xws3YRrynOErjYF-8Iw/zh-cn_image_0000002645100754.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=190BF9B111EC11440DB77D3735A239288AC09DC67DA1BDF645E2B873F2D1752F)

- 配置录制参数
配置模式：选择详情模式（即关闭Statistics Mode）。当前仅详情模式支持进行ArkTS和Native的关联分析。
- 配置开关：勾选“Local Handle”和“Global Handle”，这是关键配置。这将使Allocation专门捕获与JS-NAPI句柄相关的内存分配事件。如果底层镜像不支持该功能，则会提示“当前镜像版本不支持，请升级镜像”。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/49/v3/w8HyPAmcTVa7lcpwmhXRlQ/zh-cn_image_0000002644940852.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=91294838AE3E6A0B9BF0E2F19317F1B595959789077D868E00329629FEA7AC09)

- 配置泳道范围：勾选ArkTS Snapshot泳道。这将使Allocation在录制结尾时自动抓取一份Snapshot快照用于关联分析。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/02/v3/cnEc4ZTcRXCPl2-PMnPUuw/zh-cn_image_0000002675100559.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=DD7BB6ABBD563D52436E75B05C9B2E42B2C5181DD4768747F314DE247BF71367)


 - 启动录制：勾选了[Local Handle](#table17319174010236)开关后，如果是在应用本生命周期内首次录制local handle数据，会触发弹窗请求重启应用以便录制对应信息，此时点击OK允许重启即可。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/fb/v3/EqXFXHr8Rzi2sFf2XytwPg/zh-cn_image_0000002675020705.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=42BEF77674084F1BB46D18AE41586AD223C1AC0221329897D32E982D17BF0252)

- 运行应用程序：运行目标应用，执行相关被怀疑引入内存泄漏的业务操作，持续一段时间以增加内存压力和捕获更多数据。
- 停止录制：自动触发抓取一份Snapshot快照用于关联分析。点击快照，查找到疑似泄漏对象Proxy 。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/1/v3/_YySODJqR6OhpVeN3jqceA/zh-cn_image_0000002645100756.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=3F26FE66DF1035A11177F513F68D892DA07C6BBF3674853BB8A4262E12B7C92C)


 
2. 配置Allocation录制模板并捕获数据
 
- 定位可疑ArkTS对象：选中一个怀疑被泄漏的ArkTS对象实例（或对象类型），查看扩展标签页。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/c/v3/s0wfoZsIRPmoBb2u66PRmg/zh-cn_image_0000002644940854.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=39B059567B0EB150E34339BC9595AEFD32B173BBADD36A2AD767F559F6F32D00)

- 查看Native List：若某个ArkTS对象的distance值为1，则可以通过扩展标签页中的Native List标签页，查看所有当前与该JS对象关联的Native句柄引用，以确认该JS对象是被Local Handle或Global Handle引用的对象。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/71/v3/y4uc6Nw6SMu6UID4_XOW0A/zh-cn_image_0000002675100561.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=89428F31995474BA10D7A8F65117B0DBCCD4B7C3F4E2B58109AA821BB8B70F44)

- 关键信息：1. 句柄类型：调用栈底层的符号ArkGlobalHandle或ArkLocalHandle判断泄漏类型。

2. 调用栈：通过调用栈，可以定位到应用的Native代码（可能是ArkUI框架代码或你自己代码）中创建napi_ref的地方。

3. 注意点：
如果该JS对象节点不是一个被[Local Handle](#table17319174010236)或者[Global Handle](#table17319174010236)引用的对象，则会提示“No Detail”。

4. 如果该JS对象被Local Handle或Global Handle引用，但对应的native内存申请事件在此次录制前已完成分配，则本次录制结果无法展示该内存申请的调用栈，需重新录制。重新录制时，需将业务逻辑范围尽量提前。

 
3. 分析内存分配调用栈
 
- 排查调用栈：“Native List”标签页中的调用栈，找到对应业务代码。
- 关键排查点：1. 检查是否在适当的时候调用了对应的句柄释放接口如napi_delete_reference等。

2. 梳理这段Native代码需要引用ArkTS对象的合理性，识别这个引用的生命周期是否过长，是否应该在某个条件满足后被释放。

3. 对于napi_ref，其引用计数是关键。确保在不再需要引用时正确调用了napi_delete_reference。注意，引用计数可能因其他代码路径的创建或删除操作而意外增减。

4. 检查libuv异步调用等场景中，句柄作用域是否正确添加Handle Scope。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/c9/v3/bdRma14OToaQXDfECKPiGQ/zh-cn_image_0000002675020709.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=995B4F7B79222A164E170851ABE835A46A8741F073D1CA3A9F77FE6D11A07F04)


 


 
 

### 优化修复
1. 重新运行应用，再次使用Memory泳道监控。
2. 重复多次进出消息中心页。
3. 验证结果：
内存曲线恢复锯齿状，每次退出后回落至基线。
4. 再次抓取快照对比，多次操作后业务对象实例数量无明显增长。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d0/v3/MK6LCZ-gR9yrLiiNrgAFrA/zh-cn_image_0000002645100758.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=50BA37953E3AA7FC3C8E8D989D2377AC8B223349306985865D04F938B4846922)

 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/18/v3/1dwxioDYTXaYfdQ2fk-f1A/zh-cn_image_0000002644940856.png?HW-CC-KV=V1&HW-CC-Date=20260911T072126Z&HW-CC-Expire=86400&HW-CC-Sign=DD2CE4D9411F863340871475F480C0F653A30A6FF51A2408D2C9E9C9716FB0FE)

 
 

### 术语介绍
 

| 术语 | 解释 |
| --- | --- |
| GC Root | GC Root（Garbage Collection Root，垃圾回收引用链根节点） 是垃圾回收器进行可达性分析的起点。从GC Root能访问到的节点对象是“存活的”，否则会被回收。 |
| 引用链 | 在ArkTS中，“引用链”就是从某个GC Root（如VMRoot、FrameRoot等）出发，经过一连串的对象引用，最终到达目标对象的路径。 如果这个路径存在，则该对象是“存活”的，不会被GC回收； 如果从任何GC Root都无法找到一条到达该对象的引用链，该对象就是“不可达”的，会被标记为垃圾对象并回收。 |
| VMRoot | VMRoot是ArkTS虚拟机层面的根引用集合，代表GC遍历的起点。 |
| FrameRoot | FrameRoot是函数调用栈帧在GC遍历过程中的根节点。当函数被调用时，其局部变量和入参对象会被当前栈帧引用，从而成为GC的“可达”起点。 |
| Local Handle | Local Handle（本地句柄）是一种短期引用，用于在本地作用域（如函数调用栈）内持有对象，防止对象被垃圾回收。当作用域结束时，这些句柄会自动释放。 |
| Global Handle | Global Handle（全局句柄）例如napi_ref，用于长期持有对象引用，确保在对象生命周期内不会被垃圾回收机制回收。使用此类句柄时，开发者需要手动管理其生命周期，包括创建和销毁，以避免潜在的内存泄漏问题。 |
