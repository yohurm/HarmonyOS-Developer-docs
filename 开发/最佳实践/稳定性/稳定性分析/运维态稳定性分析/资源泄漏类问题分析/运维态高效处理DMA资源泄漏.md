# 运维态高效处理DMA资源泄漏

更新时间：2026-09-02 03:30:31

来源：https://developer.huawei.com/consumer/cn/doc/best-practices/bpta-handling-dma-resource-leaks

## 概述

DMA内存泄漏是指应用或驱动程序通过ION接口申请DMA Buffer后，在使用结束时未正常释放资源的现象。该问题会导致内核无法回收对应的物理内存，造成内存被持续占用且无法复用，进而引发系统资源的持续消耗。本文将详细介绍在运维阶段，如何依托[应用质量管理（APMS）](https://developer.huawei.com/consumer/cn/doc/app/agc-help-apms-0000002235870062)实现对DMA资源泄漏的全链路处理，涵盖监控、分析、定位及修复等关键环节。
 
 

## 运维态DMA资源泄漏分析流程

 

### 整体流程图

运维态处理流程如下图所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/13/v3/0tdaV0xeSNaN7b-Krv6kFg/zh-cn_image_0000002729540769.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=0846A1F0D1EEC9E1E2C75831BDC9D1C806AC79007C5D5A296B9397F421C6487E)

 

 
 

### 排查步骤

1. 故障预警配置：在APMS平台配置DMA泄漏监控告警规则，设置监控时段、频率和触发条件。
 
2. 问题发现与筛选：通过故障预警或主动分析页面，筛选DMA类型的泄漏问题，即MEMORY_LEAK下的ION_LEAK，查看DMA泄漏趋势与Top问题列表。
 
3. 关键信息提取：分析故障模块、发生次数、影响设备数等关键信息，定位高优先级问题。
 
4. 根因定位：通过证据链、持有链分布和现场数据，深入分析泄漏原因。
 
5. 修复与验证：根据修复建议优化代码，并验证修复效果，形成闭环。
 
 

### 指标监控与关键信息提取

 
故障分析表格会将相同根因类型的故障聚类并排序。表格会展示故障模块、发生次数（占比）、影响设备数（占比）等关键信息，开发者可以通过发生占比和故障模块结合业务实际情况找出高优的问题，并在问题状态和优先级这一栏做出标记，优先解决高优的问题。
 
资源泄漏信息详情页面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d0/v3/KdTNPOpBSCqyvzDhKj5raQ/zh-cn_image_0000002699661544.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=467C00C5A20C8C3972CD250E6EB31DA15005C9482A0D324CFB5E408A2783E32D)

 
**关键指标说明**
 
- 问题特征ID：故障模块的哈希值，同类故障模块会聚类到一起。

 
- 故障模块：发生泄漏的模块或组件，用于定位问题范围（例如Web组件、PixelMap组件、LastBuffer组件等）。
- 发生次数（占比）：泄漏问题发生的频率，帮助判断问题严重程度。
- 影响设备数（占比）：出现问题的设备数量，评估问题影响面。
- 最大泄漏数：单次泄漏的最大对象数量。

 

### 故障详情页面介绍

资源泄漏信息详情页面可以查看证据链、现场数据、线程调用栈profiler进一步深入分析泄漏的原因。通过上传.map或.so符号表文件，可将混淆后的堆栈地址还原为可读的代码行号与函数名。
 
故障详情页面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/67/v3/uNLdrs1KSk2GdtEVkaP-GA/zh-cn_image_0000002729420817.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=8B504D09CB29285E0112FF95F406732D06A15265EB78D219E976C0B53EB7D949)

 
 

## APMS平台DMA泄漏分析案例

 

### APMS故障预警

可以在故障预警平台的告警规则页面新建告警。根据实际的业务情况，选择合适监控时段、监控频率、告警触发条件以及其他告警指标，其中DMA泄漏对应的指标类型包含在MEMORY_LEAK中。
 
故障预警配置界面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/81/v3/VyVuyYY1RlOgELerpkUWSw/zh-cn_image_0000002699821452.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=2448BC79F2BCAE395B642D9357D4A6796B10480A2C0CBF37992DFAB86A707DA2)

 
创建告警之后，后台会开始收集数据。当泄漏达到告警阈值后，会触发故障预警。
 
故障预警通知如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/91/v3/cG-JOg4RSbSmd9zwaibnlw/zh-cn_image_0000002729540771.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=3C21981D95CEC2A0110CE61D190380E1D89E4E75B3B100574EADD3FC303FBEBA)

 
 

### 问题查看与聚类

 
**聚类规则说明**
 
DMA资源泄漏聚类规则请参考[DMA泄漏聚类规则](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/resource-leak-guidelines#ashmemdmagpugpu_rs聚类规则)。
 
**Top问题查看**
 
通过故障告警的指引，在故障告警页面筛选出MEMORY_LEAK的泄漏类型。单击查看按钮，即可跳转到Top问题查看页签下的MEMORY_LEAK资源泄漏问题列表。
 
故障告警页界面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/92/v3/GX_npZ_MR2Gk3Hhwn8ATRg/zh-cn_image_0000002699661546.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=062E2FAAE64A61F6508A31CA76317864DFEB05C0016F08B675745F1C151B0E00)

 
**资源泄漏信息详情Top问题**
 
在左侧页面APMS菜单下的故障分析菜单中，在资源泄漏页签下选择泄漏类型为ION_LEAK，过滤出此应用的DMA资源泄漏问题。
 
DMA资源泄漏查询界面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/fb/v3/6-CxCIPEROuqtQn2CnL4Pw/zh-cn_image_0000002729420819.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=4604C799B2DE6C670803DBB251ABB37692C794C8236D8C51E68D772D8258174E)

 
在资源泄漏信息详情中，可查看当前应用的DMA资源泄漏情况。
 
DMA资源泄漏信息详情如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/58/v3/vSr3euwETEaSSX_eA-8MdQ/zh-cn_image_0000002699821454.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=2BDF1705936EBD1293E499728B8D0981FA74CAF1AF024FA5E491A276DDB2C7F5)

 

### 根因定位与分析

 
**证据链分析**
 
故障详情页面提供了证据链和现场数据等信息，证据链展示泄漏的具体标签内容、数量、大小。证据链列表根据这些泄漏最多的组件进行一个展示，展示其DMA内存，buffer类型等。
 
证据链详情如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ad/v3/Si_IkmIfTwuMkKiqpXeTsg/zh-cn_image_0000002729540773.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=B417EEE5EC10393C03F5F686411208BB633966026D669AE16CE79504759A612F)

 
**现场数据分析**
 
现场数据页中，使用饼图展示了DMA泄漏的分布情况占比。
 
现场数据详情如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/fe/v3/uIWihbJzSlKDMYGHy1QJig/zh-cn_image_0000002699661548.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=83BED37F696D0B51995AC33BAFCE23C2F9183E02AF6A30A65C613549FC9E3D56)

 
**线程调用栈信息**
 
线程调用栈信息是发生DMA泄漏故障后，系统从堆栈中抓取的堆栈信息。可参考堆栈中的疑似泄漏点，进行堆栈还原后，结合代码分析具体的DMA泄漏根因，并进行修复。
 
堆栈信息分析：三种形式（堆栈分配详情、堆栈树分配和火焰树）用于查看方法调用关系和疑似泄漏故障处。
 
堆栈信息分析界面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/13/v3/VpNkx1hJSVGWwams_68x0w/zh-cn_image_0000002729420821.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=DF85E31390F0753865E3DAC0F5F00935A9B291DAF02E0537B43CDECA0CEC3CF9)

 
堆栈树分配界面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/45/v3/P1cdlJRBSm-2SuZ-QOtg1A/zh-cn_image_0000002699821456.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=410084CEFC20F85827B704EEADFEBCA57EBC4129929F5283305489534331CEC3)

 
火焰树界面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/7b/v3/B3TOzmQiT3KsJqSY_HKjyA/zh-cn_image_0000002729540775.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=CDF7E2AD55305067CA63019D71B66B07D12A0B0AD4DE47C9FD76F0F3C5FABC9D)

 
**下钻分析**
 
下钻分析是指从宏观汇总数据逐层深入至明细数据，以便分析DMA的泄漏趋势。平台会根据当前问题的故障特征ID，进行聚类并筛选TOP应用版本，并展示应用版本TOP5、系统版本TOP5、设备型号TOP5这三个维度的信息，帮助进一步缩小版本排查范围，明确问题在各个版本的趋势。开发者可根据此重点关注问题高发的版本及设备，更精确地定位问题。
 
下钻分析界面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/fd/v3/Bgv-jE8EQzOigAlFMCH7dA/zh-cn_image_0000002699661550.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=1CACA751E892CFDDCF905DD668196C97926D37C34D9213DACD8F29AB2D0D9C17)

 

### 修复建议验证与闭环

 
**修复建议**
 
故障详情页面会提供修复建议，开发者可以通过给出的建议优化代码。
 
一般来说，开发者需要根据引用链尝试定位并断开应用侧的引用链路，释放对应的可疑泄漏对象。
 
修复建议界面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/80/v3/1mGpbHapTCmI11i4WzVuCQ/zh-cn_image_0000002729420823.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=44EFACDE0F3B0B52605DA080766FEE8F6DAC09BC93E50AA9D2DEC236ED21D3B3)

 
**验证与闭环**
 
开发者根据修改建议，在工程中释放DMA泄漏对象。应用发布之后，更新平台告警规则，并持续关注新版本的DMA资源泄漏数据。对比修复前后的问题发生率，确认修复是否有效。
 

## 基于Operation Analyzer平台分析

Operation Analyzer平台是指DevEco Studio的Operation Analyzer插件。在DevEco Studio上可以通过此插件查看到应用对应的故障数据，数据和APMS平台上一致，开发者在IDE上也可以使用相同的方式分析运维态的泄漏问题。
 
 

### Operation Analyzer平台入口

打开DevEco Studio后，在Tool Windows栏的Operation Analyzer进入平台，单击后根据包名选择应用，再单击资源泄漏（Resource Leak）即可查看该类故障相关数据。
 
Operation Analyzer平台界面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a4/v3/4sdG36pbQ9WpokUZARdyRw/zh-cn_image_0000002699821458.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=4B40528779DDE8A939FEBBDD60754A5FF26C4EEED52E634F405D05C7B4BAF57D)

 
 

### 问题分析

**查看问题详情页**
 
开发者可自定义筛选条件筛选需要查看的问题，表格右侧是问题详情页。
 
问题详情页如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/59/v3/7LjGBQdqQ32BvCtijsjyxw/zh-cn_image_0000002729540777.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=C02697B9D6C43234CD0AFAB305E9B4919D0B714A1A6DD5342BCCDA9AA9E864CA)

 
Operation Analyzer平台的问题详情页同APMS平台功能相同，开发者可查看证据链与修复建议排查问题。如果修复建议不能支撑解决问题，可进一步查看现场数据、线程调用栈profiler进行具体分析。
 
现场数据界面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/22/v3/dCZuVnN2RuykD7V3a973dw/zh-cn_image_0000002699661552.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=FB934EA403FD4FC58DE7A9D2D9BBA866F0A2A7E6F5191358FA88540AA26EBFE9)

 
线程调用栈profiler界面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/1b/v3/sMiQSv95Sr-fp9JG7Bo3Zg/zh-cn_image_0000002729420825.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=B519E49A92108D659225DFFAC8BED3ADF5F59D4520805B2202D44C5012C13D7B)

 
 
**Operation Analyzer关联离线符号表**
 
Operation Analyzer平台提供了堆栈还原的能力，可以通过上传符号表（.so/.map/.json文件）完成堆栈还原（已有符号表则不需要上传），辅助分析问题。
 
关联离线符号表界面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/30/v3/MLZE6PmnT_eDRzPyD85R2Q/zh-cn_image_0000002699821460.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=1705CF7C0B989D8AB8E51E4CC05963F8D7B39D0D05245387147422F110E4BFC3)

 
上传符号表界面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/18/v3/JAM0EpeNTqOy_hD5vFoZiw/zh-cn_image_0000002729540779.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=F2D9312FAD1AC9F570E7892F40FF32A57B3F53B8DF2EB105BFEBABC5DFC174D1)

 
**Operation Analyzer关联代码**
 
堆栈还原后，Operation Analyzer平台可将故障处与项目代码相关联，单击故障处可跳转到对应源码中，可辅助开发者更高效地定位问题。
 
关联代码界面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/e9/v3/7XB49XfJSmSMZXEcQmJ00Q/zh-cn_image_0000002699661554.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=451015B9D00BA8F9CAB90B16732D2F80951356324DD1180CBBB239DFB8B944DA)

 
查看故障处源码步骤如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/98/v3/gqacd8gpQgOoKBXBPt99sg/zh-cn_image_0000002729420827.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=55315329B64C104590DD6BE13A9670E2E1E814BC1D3AE486FAD7380D3874812C)

 

### 问题修复

Operation Analyzer平台会给出故障分析与修复建议，开发者可根据修复建议修复问题代码。
 
问题修复界面如下所示：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/5b/v3/oNhNGUgXQ-yKfEzUA-Xy5w/zh-cn_image_0000002699821462.png?HW-CC-KV=V1&HW-CC-Date=20260911T072341Z&HW-CC-Expire=86400&HW-CC-Sign=4BDF0391184A7B84E1E01B4A114D2BCE56B93CFDEF3A8BC26759D1EEC9C7D3D6)
