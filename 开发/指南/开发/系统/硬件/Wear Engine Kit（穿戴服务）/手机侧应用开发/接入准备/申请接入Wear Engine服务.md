# 申请接入Wear Engine服务

更新时间：2026-09-09 06:54:05

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/wearengine_apply

申请Wear Engine服务前，请先参考[应用开发准备](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/application-dev-overview)（开发者需实名认证为个人开发者或者企业开发者，认证前，请先了解二者的[权益区别](https://developer.huawei.com/consumer/cn/doc/start/dbiae-0000001336403980)），确认开发环境并完成创建项目、创建HarmonyOS应用等基本准备工作，再继续进行以下开发活动。
1. 登录[AppGallery Connect](https://developer.huawei.com/consumer/cn/service/josp/agc/index.html#/)，选择“开发与服务”。
2. 在项目列表选择项目，并在应用列表下选择需要申请的应用。
3. 进入“项目设置 > 开放能力管理”页面，点击“Wear Engine”对应的“管理”。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/55/v3/HKSsBpGkRZCX7YXF9TEQeQ/zh-cn_image_0000002747291227.png?HW-CC-KV=V1&HW-CC-Date=20260911T073145Z&HW-CC-Expire=86400&HW-CC-Sign=67D234DE0E454BB1ADC7A3CDEE334D952425CCE3BCE567308A6264D83DEF99B5)

4. 进入华为开发者联盟的“管理中心”，点击“[应用服务](https://developer.huawei.com/consumer/cn/console/service/AppService)”页签下的“Wear Engine”卡片。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/50/v3/sUaFMnVjS7OpfITNjOgvIg/zh-cn_image_0000002747211145.png?HW-CC-KV=V1&HW-CC-Date=20260911T073145Z&HW-CC-Expire=86400&HW-CC-Sign=39360C95E6DB02829F94ED74212560A8F6735D3C9989123689A32457E5B470D1)


  
> [!NOTE]
> 如果无“Wear Engine”卡片，请点击右上角“自定义桌面”添加卡片。

5. 点击“申请Wear Engine服务”，同意协议后，进入权限申请页面。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a4/v3/6e1P99HoQ72S4PCDKpNLYA/zh-cn_image_0000002717771210.png?HW-CC-KV=V1&HW-CC-Date=20260911T073145Z&HW-CC-Expire=86400&HW-CC-Sign=DEA25EE6BA4D51753904F2FC6C4D242BCDD036E86A99FB4E7DD6405A614C5968)

6. 点击“HarmonyOS应用”并选择产品后，勾选必需申请的权限（个人开发者当前只可申请设备基础信息、消息通知两个基本的权限）。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/53/v3/PxNMCWVjS22V7yMfxCwOTw/zh-cn_image_0000002717611276.png?HW-CC-KV=V1&HW-CC-Date=20260911T073145Z&HW-CC-Expire=86400&HW-CC-Sign=D4B2BAB1E6DE695B2C0177FBAF2AE66302C881C46954DD83DCF05CA983F4C885)


  
> [!NOTE]
> 如选中兼容按钮，通信会将本地包名和指纹转换为兼容应用在云端存储的包名和指纹。 若选择需要兼容与旧版本穿戴应用通信的手机移动应用，则需填写归属于同账户下的 待兼容应用 与 待兼容应用包名 。 人体传感器相关权限受限开放，仅限专业研究机构使用。如未提前与华为确认，请勿申请该权限。 设备标识符权限受限开放，仅限专业合作企业使用。如未提前与华为确认，请勿申请该权限。


  **权限和设备能力类：**

  **设备基础信息**（权限）

  
穿戴设备状态管理        
穿戴设备基础信息查询：获取已配对穿戴设备列表并选定设备；支持查询穿戴设备可用空间。
7. 穿戴设备基础信息查询：支持查询电量状态；订阅低电量告警；查询或订阅穿戴设备连接状态、设备模式、充电状态。
8. 通信能力管理        
发送点对点消息/文件：手机侧“xxx(应用名)”向穿戴设备侧“xxx(应用名)”发送消息/文件。
9. 接收点对点消息/文件：手机侧“xxx(应用名)”接收穿戴设备侧“xxx(应用名)”消息/文件。
10. 消息通知能力管理        
向穿戴设备侧发送通知：手机侧应用向穿戴设备发送通知，并在穿戴设备上按模板显示；支持设置消息标题、内容、按钮。
11. 穿戴用户状态管理        
查询和订阅用户佩戴状态和订阅用户心率告警。
12. 人体传感器        
获取穿戴设备侧支持的传感器信息列表。
13. 读取穿戴设备ECG、PPG、HR传感器数据。
14. 停止读取穿戴设备侧人体传感器。
15. 运动传感器        
获取穿戴设备侧支持的传感器信息列表。
16. 读取穿戴设备ACC、GYRO、MAG传感器数据。
17. 停止读取穿戴设备侧运动传感器。
18. 设备标识符        
获取设备序列号：获取已连接穿戴设备序列号。
19. 上传申请数据权限及使用说明、用户授权路径说明，选择授权入口是否展示华为品牌LOGO后提交。

  **申请数据权限及使用说明**

  
权限：提供申请的数据权限，每个权限一行。
20. 数据使用：供使用数据权限的需求、场景、目的和方式等。
21. 数据展示路径：供所申请权限的使用场景的界面截图。可选。
22. 提供获取用户授权的界面截图及界面操作路径的文字描述。
23. 如果应用内提供了修改授权的功能，请提供修改授权的界面截图及界面操作路径的文字描述。可选。
24. 等待申请通过。

  权限审批一般需要1到2周，具体时间取决于申请的权限类型和应用发布地区。我们将视应用发布地区的相关要求进行权限开放的评估。

  如果提交的材料不满足要求，审批将不能通过。如果审批通过，即可进入开发测试阶段，完成开发测试后即可发布。

  若您的业务范围发生变动，需要修改相应的数据权限，您可以点击“修改”重新提交申请。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/92/v3/07KOmBWcQWmSel_JVgg1Jw/zh-cn_image_0000002747291229.png?HW-CC-KV=V1&HW-CC-Date=20260911T073145Z&HW-CC-Expire=86400&HW-CC-Sign=AC4E2894A7E020DFC22FB9AF845DCAB39B7B169D7D75A5713D3D76421E3561E8)
