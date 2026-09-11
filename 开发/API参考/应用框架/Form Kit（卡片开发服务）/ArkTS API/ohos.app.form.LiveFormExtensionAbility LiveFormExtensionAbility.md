# @ohos.app.form.LiveFormExtensionAbility (LiveFormExtensionAbility)

更新时间：2026-09-09 06:54:05

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/js-apis-app-form-liveformextensionability
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

LiveFormExtensionAbility（互动卡片扩展能力）模块提供互动卡片功能，包括接收创建和销毁互动卡片的通知等，继承自[ExtensionAbility](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/js-apis-app-ability-extensionability)。

> [!NOTE]
> 本模块首批接口从API version 20开始支持。后续版本的新增接口，采用上角标单独标记接口的起始版本。 本模块接口仅可在Stage模型下使用。



## 约束限制


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

为保障系统安全性和稳定性，防止LiveFormExtensionAbility滥用系统资源，系统对其能力进行管控，不支持部分模块的引用，详情请参考[附录](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/js-apis-app-form-liveformextensionability#附录)。



## 导入模块


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
import { LiveFormExtensionAbility } from '@kit.FormKit';
```



## LiveFormExtensionAbility


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

互动卡片扩展类，用于实现互动卡片的提供方功能。包含互动卡片提供方接收创建和销毁互动卡片的通知接口，开发者可在这些回调中实现卡片的初始化、数据绑定、资源清理等逻辑。[onLiveFormCreate](#onliveformcreate)在用户切换互动卡片状态为激活态时触发，用于初始化和数据绑定；[onLiveFormDestroy](#onliveformdestroy)在用户切换互动卡片状态为非激活态时触发，用于资源清理。两者形成完整的生命周期管理，应确保在create中分配的资源在destroy中正确释放。



### 属性


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Ability.Form

**元服务API：** 从API version 20开始，该接口支持在元服务中使用。


| 名称 | 类型 | 只读 | 可选 | 说明 |
| --- | --- | --- | --- | --- |
| context | LiveFormExtensionContext | 否 | 否 | LiveFormExtensionAbility的上下文环境，继承自ExtensionContext。 |




### onLiveFormCreate


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

onLiveFormCreate(liveFormInfo: LiveFormInfo, session: UIExtensionContentSession): void

LiveFormExtensionAbility实例创建完成的回调。当用户切换到互动卡片激活态时，系统会自动调用此回调，开发者可在此回调中进行卡片初始化、数据绑定等操作。

**配对调用：**

 - 与onLiveFormDestroy()方法成对使用，构成完整的互动卡片生命周期。
 - 当互动卡片切换为非激活态时，系统会自动调用onLiveFormDestroy()进行资源清理。
 - 开发者应确保在onLiveFormCreate中申请的资源在onLiveFormDestroy中正确释放，避免内存泄漏。


**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Ability.Form

**元服务API：** 从API version 20开始，该接口支持在元服务中使用。

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| liveFormInfo | LiveFormInfo | 是 | 互动卡片信息，用于标识处于激活态的互动卡片，包括卡片id等信息。 |
| session | UIExtensionContentSession | 是 | LiveFormExtensionAbility的界面会话对象，用于管理与卡片的交互会话。 |


**示例：**

```text
import { UIExtensionContentSession } from '@kit.AbilityKit';
import { LiveFormExtensionAbility, LiveFormInfo } from '@kit.FormKit';

const TAG: string = '[testTag] LiveFormExtAbility';

export default class LiveFormExtAbility extends LiveFormExtensionAbility {
  onLiveFormCreate(liveFormInfo: LiveFormInfo, session: UIExtensionContentSession) {
    console.info(TAG, `onLiveFormCreate, formId: ${liveFormInfo.formId}`);
  }
}
```



### onLiveFormDestroy


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

onLiveFormDestroy(liveFormInfo: LiveFormInfo): void

LiveFormExtensionAbility生命周期回调，在销毁时回调，执行资源清理等操作。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Ability.Form

**元服务API：** 从API version 20开始，该接口支持在元服务中使用。

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| liveFormInfo | LiveFormInfo | 是 | 互动卡片信息，用于标识处于非激活态的互动卡片，包括卡片id等信息。 |


**示例：**

```text
import { LiveFormExtensionAbility, LiveFormInfo } from '@kit.FormKit';

const TAG: string = '[testTag] LiveFormExtAbility';

export default class LiveFormExtAbility extends LiveFormExtensionAbility {
  onLiveFormDestroy(liveFormInfo: LiveFormInfo) {
    console.info(TAG, `onLiveFormDestroy, liveFormInfo: ${liveFormInfo.formId}`);
  }
}
```



## LiveFormInfo


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

互动卡片信息。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Ability.Form

**元服务API：** 从API version 20开始，该接口支持在元服务中使用。


| 名称 | 类型 | 只读 | 可选 | 说明 |
| --- | --- | --- | --- | --- |
| formId | string | 否 | 否 | 卡片id。 |
| rect | formInfo.Rect | 否 | 否 | 卡片位置和大小信息。 |
| borderRadius | number | 否 | 否 | 卡片圆角半径信息。取值大于等于0，单位vp。 |




## 附录


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

LiveFormExtensionAbility不支持以下模块的引用。


| Kit名称 | 模块名称 |
| --- | --- |
| AbilityKit | Context (Stage模型的上下文基类) UIAbilityContext @ohos.ability.featureAbility (FeatureAbility模块) @ohos.ability.particleAbility (ParticleAbility模块) @ohos.bundle.launcherBundleManager (launcherBundleManager模块) @ohos.continuation.continuationManager (流转/协同管理) |
| BasicServicesKit | @ohos.account.appAccount (应用账号管理) @ohos.account.distributedAccount (分布式账号管理) @ohos.account.osAccount (系统账号管理) @ohos.pasteboard (剪贴板) @ohos.request (上传下载) @ohos.wallpaper (壁纸) |
| BackgroundTasksKit | @ohos.backgroundTaskManager (后台任务管理) @ohos.resourceschedule.backgroundTaskManager (后台任务管理) @ohos.reminderAgent (后台代理提醒) @ohos.reminderAgentManager (后台代理提醒) |
| CalendarKit | @ohos.calendarManager (日程管理能力) |
| ConnectivityKit | @ohos.connectedTag (有源标签) @ohos.nfc.cardEmulation (标准NFC-cardEmulation) @ohos.nfc.controller (标准NFC) @ohos.nfc.tag (标准NFC-Tag) nfctech (标准NFC-Tag Nfc 技术) tagSession (标准NFC-Tag TagSession) |
| ContactsKit | @ohos.contact (联系人) |
| ArkData | @ohos.data.distributedData (分布式数据管理) @ohos.data.distributedDataObject (分布式数据对象) @ohos.data.distributedKVStore (分布式键值数据库) |
| MDMKit | @ohos.enterprise.adminManager（admin权限管理） @ohos.enterprise.deviceInfo（设备信息管理） |
| CoreFileKit | @ohos.file.picker (选择器) |
| MediaLibraryKit | @ohos.file.sendablePhotoAccessHelper (基于Sendable对象的相册管理模块) @ohos.file.AlbumPickerComponent (Album Picker组件) @ohos.file.PhotoPickerComponent (PhotoPicker组件) @ohos.file.RecentPhotoComponent (最近图片组件) @ohos.multimedia.movingphotoview (动态照片) |
| PerformanceAnalysisKit | @ohos.hidebug (Debug调试) |
| AudioKit | @ohos.multimedia.audio (音频管理) |
| CameraKit | @ohos.multimedia.cameraPicker (相机选择器) @ohos.multimedia.camera (相机管理) |
| AVSessionKit | @ohos.multimedia.avCastPicker (投播组件) @ohos.multimedia.avsession (媒体会话管理) |
| MediaKit | @ohos.multimedia.media (媒体服务) |
| NotificationKit | @ohos.notification (Notification模块) @ohos.notificationManager (NotificationManager模块) |
| TelephonyKit | @ohos.telephony.call (拨打电话) @ohos.telephony.data (蜂窝数据) @ohos.telephony.observer (observer) @ohos.telephony.radio (网络搜索) @ohos.telephony.sim (SIM卡管理) @ohos.telephony.sms (短信服务) |
| UserAuthenticationKit | @ohos.userIAM.userAuth (用户认证) |
| ArkUI | @ohos.window (窗口) |
| MapKit | sceneMap（场景化控件） |
| PaymentKit | paymentService (鸿蒙支付服务) |
| ServiceCollaborationKit | devicePicker (设备选择控制器) CollaborationDevicePicker (流转控件) |
| ShareKit | systemShare（分享） harmonyShare（华为分享） |
| VisionKit | CardRecognition（卡证识别控件） DocumentScanner（文档扫描控件） |
| ScanKit | Scan Kit（统一扫码服务） |
