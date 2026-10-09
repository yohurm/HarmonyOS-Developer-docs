# 添加Ability

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-add-new-ability

Ability是应用/元服务所具备的能力的抽象，应用的一个Module可以包含一个或多个Ability，元服务仅包含一个Ability。应用/元服务先后提供了两种应用模型：
 
- Ability组件：包含UI界面，提供展示UI的能力，主要用于和用户交互。
- ExtensionAbility组件：提供特定场景的扩展能力，满足更多的使用场景。

 

## 在模块中添加Ability
1. 在工程目录选中对应的模块，单击鼠标右键，选择**新建 > Ability **。
2. 设置**Ability名称**，单击**确认**完成创建。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/44/v3/ezk9wVcFQLaSVDQaVBEsmg/zh-cn_image_0000002778923001.png?HW-CC-KV=V1&HW-CC-Date=20261009T012522Z&HW-CC-Expire=86400&HW-CC-Sign=09E590A04358CD1F0EAA5B72B2F1DAF4E1A6356BA05AFC2C7A08915EC470F556)

 
 

## 在模块中添加Extension Ability
1. 在工程中选中对应的模块，单击鼠标右键，选择**新建> Extension Ability**，选择不同的场景类型 。
**Accessibility**：用于提供[辅助功能业务/无障碍](https://developer.huawei.com/consumer/cn/doc/doccenter-capabilities/accessibilitykit-overview)能力。
2. **InputMethod**：用于提供输入法功能业务的能力。
3. 设置**Ability名称**，单击**确认**完成Extension Ability创建。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/42/v3/RcMdscbFQz-3Hq-fHw3hVg/zh-cn_image_0000002749323918.png?HW-CC-KV=V1&HW-CC-Date=20261009T012522Z&HW-CC-Expire=86400&HW-CC-Sign=ACD9A0463B5329827E21549B9AFF8D7F176CF3F118F831A6CB621602B907111E)
