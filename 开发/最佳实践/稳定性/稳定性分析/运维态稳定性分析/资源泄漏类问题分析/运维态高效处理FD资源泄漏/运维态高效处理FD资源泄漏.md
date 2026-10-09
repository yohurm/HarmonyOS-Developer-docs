# 运维态高效处理FD资源泄漏

更新时间：2026-09-15 02:12:10

来源：https://developer.huawei.com/consumer/cn/doc/best-practices/bpta-efficiently-handle-fd-leaks

## 概述

FD（全称：File Descriptor，文件描述符）资源泄漏是一种比较常见的泄漏类型，也是应用稳定性优化的重要问题。本文档主要介绍在运维态下如何通过[应用质量管理（APMS）](https://developer.huawei.com/consumer/cn/doc/app/agc-help-apms-0000002235870062)平台进行FD资源泄漏的监控、分析、定位与修复整套处理方法。
 
 

## 运维态FD资源泄漏分析流程

 

### 标准化排查流程

**整体流程图**
 
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ff/v3/WyshFb7TStWCUcnLyyoVXg/zh-cn_image_0000002671650762.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=E87D283B392CA609019E471274E7B1DCF079876D15FE357206CF49F5AF482A6F)

 
**排查步骤**
 1. **故障预警配置：**在APMS平台配置FD泄漏监控告警规则，设置监控时段、频率和触发条件。
2. **问题发现与筛选：**通过故障预警或主动分析页面，筛选FD_LEAK类型的泄漏问题。
3. **关键信息提取**：分析故障模块、发生次数、影响设备数等关键信息，定位高优问题。
4. **根因定位**：通过证据链、持有链分布和现场数据，深入分析泄漏原因。
5. **修复与验证：**根据修复建议优化代码，并验证修复效果，形成闭环。
 

### 指标监控与关键信息提取

**资源泄漏监控信息详情**
 
故障分析表格会将相同根因类型的故障聚类并排序。表格会展示故障模块、发生次数（占比）、影响设备数（占比）等关键信息，开发者可以通过发生占比和故障模块结合业务实际情况找出高优的问题，并在问题状态和优先级这一栏做出标记，优先解决高优先级的问题。
 
如下图所示，页面入口：故障分析->资源泄漏->资源泄漏信息详情。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a1/v3/75Hpq0UrRpmzHe08UBmasA/zh-cn_image_0000002701370585.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=FAFD291FB4B219B78B6C56A790267025798B7E321CD2171E92D7A485E19BC88A)

 
**关键指标说明**
 
- 问题特征ID：故障模块的哈希值，同类故障模块会聚类到一起。

 
- 故障模块：发生泄漏的模块或组件，用于定位问题范围。
- 发生次数（占比）：泄漏问题发生的频率，帮助判断问题严重程度。
- 影响设备数（占比）：受影响的设备数量，评估问题影响面。
- 最大泄漏数：单次泄漏的最大句柄数。

 
 

**故障详情页面介绍**
 
通过点击查看按钮，进入到故障详情页面。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/80/v3/0TlnMVlFSoGy_7s4x1qP9Q/zh-cn_image_0000002701250493.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=5DD93110172406572742552A8C9F367F8D7D6C420B98DAF370C81B2E65527D42)

 
故障详情页面可以通过证据链、现场数据、句柄栈信息进一步深入分析泄漏的原因。
 
 

**证据链**
 
证据链列表根据泄漏数量的大小排序，优先查看泄漏数量最大的句柄名称。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/80/v3/5dnKbpeLTTySnMOu8fguSw/zh-cn_image_0000002671490912.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=2D5CAEC8595A87CBE8762028E72CC3DE45EE6ABF5B4067E38210FD39C31DC826)

 
**现场数据**
 
现场数据展示了当前FD泄漏的Top10的句柄名称，可结合代码、日志分析对应的FD泄漏对象。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/14/v3/gBbtGWV9TMOWxavXtIeOhQ/zh-cn_image_0000002671650764.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=87731A5E528F9656DBC858CA4240E017DE58E419DC7028389563DE8EA95FD7E4)

 
**句柄栈信息**
 
句柄栈信息中可查看对应的堆栈信息，以及疑似泄漏点。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/65/v3/Z49YIi9PSEKeKamkBbO3wg/zh-cn_image_0000002701370587.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=077A60BC48F481C9FAD9600F384ED2DB2992AE85EF45A68C4F494F32FCA2E0CB)

 
 

## APMS平台FD泄漏分析案例

 

### 灰度任务创建

应用灰度特性是一种运维态功能，用于精准采集故障日志。开发者在端侧集成应用灰度采集功能（可参考：[应用灰度采集介绍](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/hiretrieval-intro)）后，该应用可参与应用灰度活动。通过云端平台进行[灰度采集](https://developer.huawei.com/consumer/cn/doc/app/agc-help-apms-gray-scale-collect-0000002619401669)，可圈选部分设备开启故障日志精准采集，帮助开发者快速定位故障。
 
 

### APMS故障预警

在故障预警平台的告警规则页面新建FD泄漏告警。根据实际的业务情况，选择合适监控时段、监控频率、告警触发条件以及其他告警指标，其中FD泄漏对应的指标类型为FD_LEAK。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/e6/v3/OZ-mucMIRIS62NZ29L8AJQ/zh-cn_image_0000002701250495.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=ED9916B196D2D9BD703232599174136B303146FB67679995864B8A54544A9534)

 
创建告警之后，后台会开始收集数据。当达到设置的告警阈值后，会触发故障预警。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/96/v3/kBszrQBGTMaLuIJOj42_QQ/zh-cn_image_0000002671490914.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=0C275F1F564ECD59E560AE9244CF2F1AA355246A87C6383E80F8FAE6229ADE86)

 
 

### 问题查看与聚类

**聚类规则说明**
 
FD资源泄漏聚类规则请参考[句柄泄漏聚类规则](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/resource-leak-guidelines#句柄泄漏聚类规则)。
 
**问题查看**
 
- **Top问题查看**

 
通过故障告警的指引，在故障分析页面筛选出FD_LEAK的泄漏类型。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/0b/v3/Kg4R8zziQpmNX0yhWeTowg/zh-cn_image_0000002671650774.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=44C0F2A2432B22353D62C1941C33E22986AACC6EF00A72F7E4CB4AD117877A55)

 
点击查看按钮，即可跳转到Top问题查看页签下的FD资源泄漏问题列表。
 
 

- **资源泄漏信息详情Top问题**

 
在左侧页面APMS菜单下的故障分析菜单中，在资源泄漏页签下选择泄漏类型为FD_LEAK，点击查询按钮，过滤出此应用的FD资源泄漏问题。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/33/v3/b_QD0exJTYWXgA6V6W_cjA/zh-cn_image_0000002701370625.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=2969582102D6712B8F5E91A894C6D17E2406902C2F4AA75F55FE3D40B45FDBE5)

 
在资源泄漏信息详情中，可查看当前应用的FD资源泄漏情况。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/7a/v3/gmDfYIxMRjaoXIV5nC7VTw/zh-cn_image_0000002701250559.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=FE0A1981B2677E12F221A83BB193025E353762BCF56F38D3DDA2F38C9AB14DA3)

 
 

### 根因定位与分析

过滤出FD资源泄漏故障列表后，点击查看按钮，进入到问题个例分析详情页，可查看当前故障的分析报告，包含故障发生时间、泄漏句柄、故障模块、版本信息以及修复建议等。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ec/v3/3OygwVlsQJe9hKeiFYwHmQ/zh-cn_image_0000002671490976.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=80CE9866725827DE77D7E22BF4006C8B2ACF9ABD03522486A0E8CA2CA8D54884)

 
**证据链分析**
 
证据链列表中按照泄漏数量倒序排序，将FD泄漏的句柄名称展示出来，开发者可根据泄漏数量较大的句柄名称，结合代码分析FD泄漏根因。同时提供了日志下载功能，便于进一步分析。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/1f/v3/ZboaHFLoRIq77rmfuQ9pWw/zh-cn_image_0000002671650846.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=7A2FC134C3D7C25DB82EA416E27103CBA8B04BA53BF98C280B37EA380C41C237)

 
**现场数据分析**
 
现场数据页中，将展示Top10的泄漏句柄名称，开发者根据泄漏数量较大的句柄名称，并结合代码分析FD泄漏根因。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4e/v3/jrC_59OpSP-_jBM2QVgRXA/zh-cn_image_0000002701370681.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=2E1D43D06BE016C0D33DC6055A4A17C29BF871DF763DD75CFF8B1D8311D1A82D)

 
**句柄栈信息分析**
 
句柄栈信息是发生FD泄漏故障并达到一定条件后，系统从堆栈中抓取的堆栈信息，存在一定的滞后性。开发者可参考堆栈中的疑似泄漏点，进行堆栈还原后，结合代码分析具体的FD泄漏根因，并进行修复。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/f7/v3/xRiYsXIFT9CZivSBxYdV1Q/zh-cn_image_0000002701250593.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=BF090CAEF64DF9AEB9C76666A567A10387336E68E0837A8806D840DE321125BF)

 
**下钻分析**
 
下钻分析的核心逻辑是从一个汇总的指标或表象问题出发，将其拆分成多个组成部分，然后挑出最关键的线索继续向下拆分，不断重复这个过程，直到定位到具体的根因。平台会根据故障特征ID进行聚类并筛选Top应用版本，系统版本以及设备型号。开发者可根据此重点关注问题高发的版本及设备，更精确的定位问题。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/68/v3/pTXPrZD7THmlNbQ0_WhIEw/zh-cn_image_0000002671491006.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=32BE9E1698076EA68EACB983F490FCEEE364724C44E87EC02E8D65C48818B797)

 
 

### 修复建议验证与闭环

**修复建议**
 
故障详情页面会提供修复建议，开发者可以通过给出的建议优化代码。
 
一般来说，开发者需要根据引用链尝试定位并断开应用侧的引用链路，释放对应的可疑泄漏对象。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/2b/v3/pEccklHjQf6zXgieTdPRTQ/zh-cn_image_0000002671650858.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=26C864284BEA40CA398924E92C1ED406DC48D27759ACD85E364539A432C7CFD2)

 
**问题修复与闭环**
 
- **问题修改**

 
开发者根据修改建议，在工程中释放FD泄漏对象。
 
- **问题标记**

 
优化之后，可以在分析页面对对应的FD泄漏对象标记。
 
- **应用发布**

 
应用发布之后，更新平台告警规则，并持续关注新版本的FD资源泄漏数据。对比修复前后的问题发生率，确认修复是否有效。
 
 

## 基于Operation Analyzer平台分析

 
Operation Analyzer平台是指DevEco Studio的Operation Analyzer插件，通过该插件查看到应用对应的故障数据，数据和APMS平台上一致，开发者使用该插件以相同的方式分析运维态的泄漏问题。
 

### Operation Analyzer平台入口

 
打开DevEco Studio后，在Tool Windows栏的Operation Analyzer进入平台，点击后根据包名选择应用，再点击资源泄漏（Resource Leak）即可查看该类故障相关数据。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/09/v3/UdTXvg1dQjONoyBsBmgi5g/zh-cn_image_0000002701370683.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=F91A363DA31B9AD8BAC6B397337A00B60065D6ACCA32D89E51D16FBDDF892E9C)

 

### 问题分析

**证据链分析**
 
证据链列表中按照泄漏数量排序，将FD泄漏的句柄名称展示出来，开发者可根据泄漏数量较大的句柄名称，结合代码分析FD泄漏根因。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/e9/v3/BhGHR27CTOG6qZKwE-XLFA/zh-cn_image_0000002701250595.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=C235A1395F6A908174993489E4AECDE6005D42C4DBB244276B49AAEA736798D1)

 
**现场数据分析**
 
现场数据页面将展示Top10的泄漏句柄名称，开发者根据泄漏数量较大的句柄名称，并结合代码分析FD泄漏根因。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/21/v3/HcfbgqkNT3u4iAywxTFaOA/zh-cn_image_0000002671491008.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=DCC9850971675CB0C38DB1E0966F94A4921293C8E6A060321AA65C0C32CFDCA0)

 
**句柄栈信息分析**
 
句柄栈信息中将抓取的堆栈信息中疑似泄漏点进行展示，开发者进行堆栈还原后，结合代码分析具体的FD泄漏根因，并进行修复。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/8d/v3/lJDDbfYvQbqkf8yzOV2J6g/zh-cn_image_0000002671650860.png?HW-CC-KV=V1&HW-CC-Date=20261009T012643Z&HW-CC-Expire=86400&HW-CC-Sign=56D853BB99EA6A716B37D6A4A81F57129ACA3E201EB4D59FA979E88661B9D033)
