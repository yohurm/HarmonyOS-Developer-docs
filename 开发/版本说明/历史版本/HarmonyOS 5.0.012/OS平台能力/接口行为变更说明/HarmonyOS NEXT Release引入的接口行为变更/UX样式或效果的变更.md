# UX样式或效果的变更

更新时间：2026-10-08 10:09:13

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-releases/changelogs-ux-b071

## showToast接口TOP_MOST模式行为变更

**变更原因**
 
toast层级过高，会挡住权限弹窗等敏感内容，存在安全隐患。
 
**变更影响**
 
此变更涉及应用适配。
 
API version 12及以后，TOP_MOST模式弹出的Toast的层级发生改变，即：
 
变更前：Toast层级较高，可以悬浮显示在输入法、系统授权弹窗之上。输入法弹出后不避让，保持在原来的位置。
 
变更后：
 1. Toast不能悬浮显示在输入法之上，如果Toast与输入法有重叠，则将Toast避让到输入法上方固定80vp处。
2. Toast在系统敏感内容显示时不显示或被覆盖。
3. 在画中画窗口和悬浮窗中不支持创建TOP_MOST模式的Toast。
  

| 变更前 | 变更后 |
| --- | --- |
| ![](assets/UX样式或效果的变更/file-20260515134951220-0.gif) | ![](assets/UX样式或效果的变更/file-20260515134951220-1.gif) |
 
  

| 变更前 | 变更后 |
| --- | --- |
| ![](assets/UX样式或效果的变更/file-20260515134951220-2.png) | ![](assets/UX样式或效果的变更/file-20260515134951220-3.png) |
 
  

| 变更前 | 变更后 |
| --- | --- |
| ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/61/v3/WGFfGlspSC6VuGJup9HaAA/zh-cn_image_0000002087445941.png?HW-CC-KV=V1&HW-CC-Date=20261009T012725Z&HW-CC-Expire=86400&HW-CC-Sign=4F4175E7FA67E978FAD011CF5502467F348CE5802B9804FDFF6F1A2842ABA532) | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/b7/v3/vSIUZiaKRF2O9wb_6uaY5g/zh-cn_image_0000002051328530.png?HW-CC-KV=V1&HW-CC-Date=20261009T012725Z&HW-CC-Expire=86400&HW-CC-Sign=E4C14DE827C3375D7064298BC709E35B1C2A6CAAC28F56AC0851D6454F82CDE1) |
 
 
**起始API Level**
 
11
 
**变更的接口/组件**
 
showToast接口
 
**适配指导**
 1. 对于输入法的场景，开发者可以设置高度将Toast放到合适的位置，主动避开输入法。
2. 对于敏感内容的场景，开发者无法适配。
3. 对于画中画和悬浮窗的场景，开发者可以改为使用DEFAULT模式。
 
 

## 模态UIExtension创建默认行为变更

**访问级别**
 
公开接口
 
**变更原因**
 
通过各个应用或者kit提供的开放能力创建出来的模态UIExtension，可能被三方应用组件或窗口遮挡，造成安全风险。
 
各个应用或者kit是通过CreateModalUIExtension这个系统接口来创建模态UIExtension，
 
本质上是这个接口的默认行为发生了变化
 
**变更影响**
 
此变更涉及应用适配。
 
模态UIExtension不允许被不安全窗口遮挡，拉起模态UIExtension时，会隐藏三方应用已创建的不安全窗口和组件，并阻止三方应用创建新的不安全窗口
 
变更前后行为如下表所示：
  

| 变更前 | 变更后 |
| --- | --- |
| 允许不安全窗口遮挡，允许三方应用组件遮挡 | 不允许不安全窗口遮挡，不允许三方应用组件遮挡 |
 
 
不安全窗口的定义新增宿主创建的Dialog窗口，变更前后不安全窗口包含的窗口类型如下表所示。
  

| 变更前 | 变更后 |
| --- | --- |
| 非系统全局悬浮窗 宿主创建的非系统子窗 | 非系统全局悬浮窗 宿主创建的非系统子窗 宿主创建的非系统Dialog窗口 |
 
 
**变更前**：
 
图中的分享框就是一个模态UIExtension，该组件弹出后，带有"Sub Window"字样的子窗不会被隐藏，并且盖在分享框的上面。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/04/v3/y6D8a3LrTgu4yoo7VKKdzw/zh-cn_image_0000002078063544.gif?HW-CC-KV=V1&HW-CC-Date=20261009T012725Z&HW-CC-Expire=86400&HW-CC-Sign=DCAEA4592D5CB9964445D50C7D9EA02E8B7986A3AB8A0F49A4258B48A5EE0B96)

 
**变更后**：
 
图中的分享框就是一个模态UIExtension，该组件弹出后，带有"Sub Window"字样的子窗被隐藏，关闭分享框后这个子窗重新展示。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/6d/v3/YAwB0x4_SC6OowHE-sodIg/zh-cn_image_0000002113588317.gif?HW-CC-KV=V1&HW-CC-Date=20261009T012725Z&HW-CC-Expire=86400&HW-CC-Sign=CCA1B2E6AF5B42729F9423C6FEEFFF2A428A8EFE70F287668A7258FAEB842CF9)

 
 

**起始API Level**
 
11
 
**变更的接口/组件**
  

| kit名称 | 接口名/组件名 |
| --- | --- |
| Core File Kit | DocumentViewPicker组件 |
| Store Kit | productViewManager.loadService productViewManager.loadProduct |
| Media Library Kit | PhotoAccessHelper.createDeleteRequest PhotoAccessHelper. removeAssets PhotoAccessHelper.showAssetsCreationDialog PhotoAccessHelper.createAssetWithShortTermPermission PhotoAccessHelper.select |
| Scan Kit | scanBarcode.startScanForResult |
| Ads Kit | advertising.showAd |
| ShareKit | SystemShare.show |
| Map Kit | sceneMap.chooseLocation sceneMap.queryLocation sceneMap.selectDistrict |
| Account Kit | authentication.executeRequest.LoginWithHuaweiID authentication.executeRequest.AuthorizationWithHuaweiID extendService.verifyAccount extendService.startAccountCenter loginComponent.LoginWithHuaweiIDButton loginComponent.LoginPanel loginComponent.startFacialRecognitionVerification realName.startFacialRecognitionVerification shippingAddress.chooseAddress minorsProtection.verifyMinorsProtectionCredential minorsProtection.leadToTurnOnMinorsMode minorsProtection.leadToTurnOffMinorsMode |
| ArkUI | TextInput输入框组件(仅系统密码自动填充服务场景涉及, InputType设置为USER_NAME/Password/NEW_PASSWORD类型) |
 
 
**适配指导**
 
默认行为变更，应注意变更后的行为是否对整体应用逻辑产生影响。
 
 

## 安全控件offset属性设置行为变更

**变更原因**
 
应用在集成安全控件时，安全控件通过offset属性设置相对父组件的偏移后，若被父组件裁剪不能完整显示时，其仍可响应点击授权，存在隐私安全风险，可能被恶意应用利用。
 
> [!NOTE]
> 该变更在10月18日更新的系统ROM版本引入，ROM版本号为NEXT.0.0.72。

 
**变更影响**
 
此变更涉及应用适配。
 
变更前：
 
应用在集成安全控件时，安全控件通过offset属性设置相对父组件的偏移后，且被父组件裁剪不能完整显示时，其仍可响应点击授权。
 
例如：
 
安全控件设置offset属性后被父组件裁剪不能完整显示时，安全控件仍可响应点击授权。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a1/v3/7nDfhWznQOGp47BBahLc4Q/zh-cn_image_0000002087445945.png?HW-CC-KV=V1&HW-CC-Date=20261009T012725Z&HW-CC-Expire=86400&HW-CC-Sign=4FD69D2CF46DFB567D20846E53B45296F76528177682C63BF88A5C14C41281E6)

 
变更后：
 
应用在集成安全控件时，安全控件通过offset属性设置相对父组件的偏移后，且被父组件裁剪不能完整显示时，其不可响应点击授权。
 
例如：
 
安全控件设置offset属性后被父组件裁剪不能完整显示时，安全控件不响应点击授权。
 
**起始API Level**
 
10
 
**变更的接口/组件**
 
@internal/component/ets/location_button.d.ts中 LocationButton接口。
 
@internal/component/ets/save_button.d.ts中 SaveButton接口。
 
@internal/component/ets/paste_button.d.ts中 PasteButton接口。
 
**适配指导**
 
安全控件设置offset属性后被父组件裁剪不能完整显示时，可通过调整offset({x: value, y: value})中x或y值，使得安全控件完整显示。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/cb/v3/5SwriCQ1Q1uKReUbCB58Ww/zh-cn_image_0000002051328534.png?HW-CC-KV=V1&HW-CC-Date=20261009T012725Z&HW-CC-Expire=86400&HW-CC-Sign=35EF0C5BE0C653BB010A66D78D8D1C4BFF4D9ECC5067A56D13238D8EAE391358)
