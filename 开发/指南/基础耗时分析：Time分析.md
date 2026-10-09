# 基础耗时分析：Time分析

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-insight-session-time

## 功能介绍

开发应用或元服务过程中，如果遇到卡顿、加载耗时等性能问题，开发者通常会关注相关函数执行的耗时情况。DevEco Profiler提供的Time场景分析任务，可在应用/元服务运行时，展示热点区域内基于CPU和进程耗时分析的调用栈情况。
 
Time模板支持的泳道包括：User Trace、Callstack。
 
 

## 函数耗时分析及优化

在设备连接完成后，可按照如下方法查看耗时分析结果：
 1. 构建应用前请参考模块级[build-profile.json5文件](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-hvigor-build-profile)，增加strip字段并赋值为false，不移除当前模块.so文件中的符号表、调试信息。采集函数栈解析符号需要附带符号表信息，无符号表信息可能采集不到函数名称，因此请按照下图进行配置。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/c0/v3/0gBhf6K4R9WVVChCrPSR8w/zh-cn_image_0000002779082749.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=29681BEFF5815FA1BD1BAF31F0458A0824955C74F4CC3CD793314D6CAB9D5379)

2. 创建Time任务并录制相关数据，操作方法可参考[性能问题定位：深度录制](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-deep-recording)，或在会话区点击![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/23/v3/QmoeMShrQju2pGS76ZrSLw/zh-cn_image_0000002749323810.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=8E36E7DA056D9C2665C2CC48D4951F673FC0733CA95017466D7CA4BF9081AE7F)图标，导入历史数据。在录制前单击录制按钮旁![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/aa/v3/Pt8puVWtQv669WOmIm1r-w/zh-cn_image_0000002778922903.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=FCD1F4C24DC9D7C8B1FCE0B54E2F8FEDB567C43114631E9C5887A1CCA4D3402F)按钮，点击**录制设置**指定要录制的泳道。
- **User Trace**：用户自定义打点泳道，基于时间轴展示当前时段内用户使用hiTraceMeter接口自定义的打点任务的具体运行情况。

3. **Callstack**：ArkTS和Native混合函数调用泳道。基于时间轴展示各线程的CPU使用率，以及在一段时间内的混合调用栈。调用栈类型会分为开发者或系统的ArkTS以及Native代码两类。由于隐私安全政策，已上架应用市场的应用不支持录制此泳道。Callstack基于采样模式采集数据，默认采样间隔是500微秒。耗时小于500微秒的函数，Details区域时间相关数据可能存在误差，可通过录制过程中多次触发该函数，根据其耗时百分比判断是否为热点函数。

4. 在**Callstack**子泳道上长按鼠标左键并拖拽，框选要展示分析的时间段。**Details**区域会显示所选时间段内的函数栈耗时分布情况，**Heaviest Stack**区域会展示出**Details**区域选择节点所处的耗时最长的完整调用栈。函数栈耗时分布有两种展现方式：调用树（默认展示方式）、火焰图。
在调用树中，“Weight”字段表示当前函数的总执行时间，“Self”字段表示函数自身的执行时间，两者之差为当前函数所调用的子函数执行时间之和，“Average Duration”字段表示函数自身的平均执行时间，“Category”字段表示函数调用类型。

5. 打开页面上方的**火焰图**开关，函数调用栈将以火焰图的形式展示。其中，横轴表示函数的执行时长，纵轴表示调用栈的深度。
> [!NOTE]
> 火焰图条块支持搜索，搜索结果不匹配的条块会被置灰。 “Ctrl+鼠标滚轮”的操作，或单击该区域右上角的 、 可放大和缩小火焰图的时间轴比例，单击 可恢复时间轴比例为初始状态。 “Shift+鼠标滚轮”的操作可左右横向调整可视区间，单独操作滚轮可上下纵向调整可视区间。 选中节点，单击该区域右上角的 ，点击添加面包屑。添加面包屑后，该节点成为根节点，耗时占比为100%，子节点的耗时占比相对于该节点重新计算。 在火焰图中选中任一节点，使用“Alt+左键”可将该节点左置底并将其占比放大到100%，其上从属节点按同比例放大显示。该快捷操作同样适用于列表方式，用于将指定节点置顶并截取所属下级节点。


  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/19/v3/cP2WMop1S1y_J3hQMGcSsw/zh-cn_image_0000002778922891.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=8D9B8D0B05CEC40FFA6CD688C0984DE4319247F1546F52F5CBE9FD1878D45BE6)


6. 在**Callstack**泳道上长按鼠标左键并拖拽，框选要展示分析的时间段。
**Summary**列表展示框选时段内，所有Native线程的CPU占用率的峰值、谷值、平均值。

7. **Callstack**列表展示框选时段内，所有Native线程的函数热点。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/7b/v3/lUbou6C9SReu4RqVi3PyHQ/zh-cn_image_0000002778922893.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=9B12A57F8C88EB10077BEC541D6452B6C0F40CB89B9E12E9281F555BCA6CFABB)


8. 悬浮到节点，显示以此节点为根按钮，点击添加面包屑。添加面包屑后，该节点成为根节点，耗时占比为100%，子节点的耗时占比相对于该节点重新计算。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/08/v3/uELIrzzgSd-wBkddZy8jpA/zh-cn_image_0000002779082751.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=C0E708A2964CE0282F8F1987FBC17F577A13C0BB0A3C6AC8B4CF3F7FA1EC2BFA)


  

  ## 离线符号分析

  DevEco Profiler提供离线符号解析能力，基于携带符号表信息的so库进行分析，可把符号地址解析为具体函数名称，便于定位函数位置。

  对于有so库路径和偏移地址的采样数据，如图所示，通过导入对应的携带符号表信息的so库进行解析，补充release so库中缺失的符号表信息（包括系统so库，用户自编译的so库，三方库）。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/06/v3/R_as5EmvSlm3OP9AzoY5bw/zh-cn_image_0000002749323804.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=D88249B2D052FA12CE36E8F2C6F255E125ACDB6E5C3783C8245F5AA1A5541ABF)


  您可以通过点击工具栏![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/c0/v3/HYaUOZyiRXuFozM48hxFHA/zh-cn_image_0000002778922899.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=4BC9F564B448E13841D1B34B5FDF6DF8E8F16F30021DE3742887007A7D778A8D)按钮，导入包含debug信息的so库。

  
> [!NOTE]
> 离线导入携带符号表信息的so库，需要严格保证与release版本的so库保持同一优化等级（如-O1, -O2, -O3等）。可以在CMakeLists.txt文件中查看或配置编译优化等级。 离线导入携带符号表信息的so库，需要尽可能与release版本的so库编译选项保持一致，防止so库起始地址不一致，影响解析正确性。


  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/0/v3/Tz1OdwB-TVCUiW46elWHOQ/zh-cn_image_0000002749483680.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=3C1EEE87CBAE27F6CE0C1E65C16663B94BA23E494C93AA37E25788067D56AB81)


  

  ## 查询自定义打点信息

  相较于异步调度，DevEco Profiler当前基于采样分析的Time任务更善于分析同步性能问题。如开发者需要分析异步调度延时等问题，可先在ArkTS代码中进行自定义打点，当元服务/应用在Time分析过程中触发打点后，DevEco Profiler会将这些打点的Trace数据解析后，以任务方块形式呈现在“User Trace”泳道中。

  单击**User Trace**泳道的![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d7/v3/Dn647ZgERpOp5APVAIrDDg/zh-cn_image_0000002749483686.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=659915B2926DB7F0F9C23C58BED53BFBE0F21CAE869A4B948F2ECE64AF402D30)图标下拉列表，可以设置子泳道是按照Task Name维度还是Thread ID维度显示。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/14/v3/MK1akqdcSbiXwjCN1xs4TQ/zh-cn_image_0000002749323812.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=B846E8A33EFE3ADC31190377C8E2365282CFE436A26ED24CEFD3AE2250BE533F)


  在**User Trace**子泳道上长按鼠标左键并拖拽，框选要展示分析的时间段，获取该时间段内的用户打点信息。

  
**Statistics**页签：显示当前任务泳道在所选时间段内的打点任务统计信息，包括任务的名称、同一任务执行的次数、平均持续时长、最长持续时间和最短持续时间。通过这些统计信息，开发者可直观地了解打点任务的执行频率、持续时间偏差等，方便定位。
- **User Trace**页签：将所选时间段内的所有任务都一一列举出来，包括任务的名称、ID、起始/结束时间、持续时长等。

 
单击**User Trace**子泳道中的任意一个任务块，**Details**区域将展示该任务块的详细信息。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/35/v3/FpUQtKZTSw-NPpTo_KhtAg/zh-cn_image_0000002779082753.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=7F5B91C1C5640403D47D9C6561B0936F75EBDEAD2F5EA9BE86F47303336237A1)
