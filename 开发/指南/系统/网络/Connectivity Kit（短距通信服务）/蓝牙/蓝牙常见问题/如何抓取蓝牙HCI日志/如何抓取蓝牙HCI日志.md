# 如何抓取蓝牙HCI日志

更新时间：2026-09-23 02:54:26

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/bluetooth-hci-log-capture

## 简介

蓝牙/全场景开发者，可以通过开发者模式，一键采集蓝牙连接HCI日志，高效完成APP连接性能调试。该功能具有以下特点：
 
- 一键采集：操作简单，下拉通知栏点击开发者模式卡片，点击收集按钮即可完成HCI日志采集。
- 本地管理：抓取的HCI日志保存在文件管理可访问路径下，日志文件由手机用户管理。

 
> [!NOTE]
> 蓝牙HCI日志抓取功能面向开发者提供便捷高效的蓝牙HCI日志抓取能力。 开发者抓取蓝牙HCI日志功能从API版本26.0.0开始支持，目前支持Phone、Tablet。 Release版本出于数据安全与隐私保护，会屏蔽HCI日志中蓝牙报文的payload数据，仅保留Header信息，因此若HCI日志报文数据解析不完整属正常现象。

 
  

## 操作步骤

  

### 步骤一：开启开发者模式

在调测手机上进入开发者模式，开启方法请参考 **[开启开发者选项](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-developer-mode#section530763213432)**。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/88/v3/zFmyiTFmTF6FCLD2jUVCTA/zh-cn_image_0000002778932197.png?HW-CC-KV=V1&HW-CC-Date=20261009T012638Z&HW-CC-Expire=86400&HW-CC-Sign=834184B0DCD56A3ECE04EF748EAED997C203F7433AE5E434101CF1DCF5B4FC8C)

 
  

### 步骤二：连接蓝牙设备进行调试

开启手机蓝牙，连接需要调试的蓝牙外设，进行设备连接调试或问题复现操作。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/be/v3/vP_wZIX3S3qORvDI1NzONw/zh-cn_image_0000002749333114.png?HW-CC-KV=V1&HW-CC-Date=20261009T012638Z&HW-CC-Expire=86400&HW-CC-Sign=9A93BC65D9C7528DD5707FF2E1EFD7C37636F1868321C816B191ACA5CA5C0B13)

 
  

### 步骤三：一键采集HCI日志

连接调试操作完毕后，下拉通知栏，点击**开发者模式**卡片，卡片下方会显示**收集**按钮，点击即可一键采集HCI日志。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/e1/v3/h0ApwXpqRzaF30ATmDQUqA/zh-cn_image_0000002749492998.png?HW-CC-KV=V1&HW-CC-Date=20261009T012638Z&HW-CC-Expire=86400&HW-CC-Sign=F8B2287950DDC7972989D48509C6A93BE84B25659135F9782F190C0DC8FADED8)

 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d1/v3/XrFsX8AaSUOIOng8uYeqyg/zh-cn_image_0000002779092057.png?HW-CC-KV=V1&HW-CC-Date=20261009T012638Z&HW-CC-Expire=86400&HW-CC-Sign=47E6F5968A77D5F2EE8A9194CE659BC46B62A4366BEF5D94A449BEC82F3C2C15)

 
> [!NOTE]
> 点击"收集"后，系统开始采集HCI日志，采集过程约30秒，请耐心等待。 下拉通知栏的 开发者模式卡片 可以被移除，移除后将无法抓取HCI日志。若卡片已被移除，需在保证 开发者模式开启 的情况下， 重启手机 ，卡片才可重新生效。请勿随意移除开发者模式卡片。

 
  

### 步骤四：查看与导出HCI日志

采集完成后，进入手机文件管理，选择**我的手机**，点击**Documents**目录，即可找到日志压缩包
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/22/v3/uVkxNW_qQvyIPChkhzJxIw/zh-cn_image_0000002778932199.png?HW-CC-KV=V1&HW-CC-Date=20261009T012638Z&HW-CC-Expire=86400&HW-CC-Sign=ECAD40AAFB45269A21D3146BD81A553A7711A115DF0D2DFAD713496DDF77318C)

 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/8a/v3/bIn_Y5HbT36y0_gmCg__vw/zh-cn_image_0000002749333116.png?HW-CC-KV=V1&HW-CC-Date=20261009T012638Z&HW-CC-Expire=86400&HW-CC-Sign=2FD101A3AF93629EE8915E0B4B6D5DDDB0A133B9BF0C7121E1C352E9447AF7F6)

 
通过**华为分享**、**三方应用**等方式，将日志压缩包分享到PC侧。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/f0/v3/slLTXo3wQzy_9Av50CCqDA/zh-cn_image_0000002749493000.png?HW-CC-KV=V1&HW-CC-Date=20261009T012638Z&HW-CC-Expire=86400&HW-CC-Sign=924864EAA273C98652731F5AF6E7B40DC39947FA1DDDAA214C23E3A7B7FD46B5)

 
> [!NOTE]
> 抓取的HCI日志仅保存在手机本地，不自动上传，日志文件完全由手机用户管理。

 
  

### 步骤五：在PC侧分析HCI日志

将日志压缩包从手机导出至PC后，使用蓝牙HCI日志分析工具（如Ellisys Bluetooth Analyzer、Wireshark等）打开日志文件进行分析。
