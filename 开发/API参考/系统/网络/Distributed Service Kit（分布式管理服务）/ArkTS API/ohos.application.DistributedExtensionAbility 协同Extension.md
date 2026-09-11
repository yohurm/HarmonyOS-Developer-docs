# @ohos.application.DistributedExtensionAbility (协同Extension)

更新时间：2026-09-09 06:54:05

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/js-apis-distributedextensionability
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

DistributedExtensionAbility（分布式扩展能力）模块提供了面向多设备限定协同场景（如：面向穿戴和手机间的专有通讯服务）下的扩展能力基类。

该模块作为多设备限定协同场景扩展能力基类，主要包含以下能力：

 - **生命周期管理**：提供onCreate（创建）、onCollaborate（协同）、onDestroy（销毁）三个生命周期回调，覆盖协同Extension从创建到销毁的完整生命周期，使应用能够在不同阶段执行初始化、协同决策和资源清理等业务逻辑。
 - **协同决策**：通过onCollaborate回调，应用在被跨设备拉起过程中，可根据调用方传输的协同参数自主决定是否接受协同请求（ACCEPT/REJECT），从而灵活控制协同流程是否继续。
 - **上下文环境**：提供distributedExtensionContext上下文环境，支持连接和断开远端ServiceExtensionAbility，实现跨设备的服务调用与数据互通。


协同Extension的核心类结构及其与上下文、自定义子类的关系如下图所示。


![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/1c/v3/6QQcgCn9R8WU6rUxdSsEcg/zh-cn_image_0000002717613590.png?HW-CC-KV=V1&HW-CC-Date=20260911T072854Z&HW-CC-Expire=86400&HW-CC-Sign=7FF1E9004F8E58027943D7A42194A426EC5A1858D183B94DC2E829D38FA02507)


如上图所示：

 - **继承关系**：DistributedExtensionContext 继承自 ExtensionContext（扩展上下文）；开发者自定义子类继承自 DistributedExtensionAbility。
 - **组合关系**：DistributedExtensionAbility 持有 context 属性，类型为 DistributedExtensionContext，提供连接/断开远端 ServiceExtensionAbility 等协同能力。


开发者通过继承 DistributedExtensionAbility 并实现 onCreate、onCollaborate、onDestroy 生命周期回调，即可获得多设备限定协同场景相应能力。

> [!NOTE]
> 本模块首批接口从API version 20开始支持。后续版本的新增接口，采用上角标单独标记接口的起始版本。 本模块接口仅可在Stage模型下使用。



## 导入模块


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
import { DistributedExtensionAbility } from '@kit.DistributedServiceKit';
```



## DistributedExtensionAbility


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable



### 属性


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

**模型约束**：此接口仅可在Stage模型下使用。

**系统能力**：SystemCapability.DistributedSched.AppCollaboration

**设备行为差异：** 该接口在不支持分布式业务的Wearable设备不生效。


| 名称 | 类型 | 只读 | 可选 | 说明 |
| --- | --- | --- | --- | --- |
| context | DistributedExtensionContext | 否 | 否 | DistributedExtension（协同Extension）的上下文环境，继承自ExtensionContext。 |




### onCreate


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

onCreate(want: Want): void

Extension生命周期回调，在创建时回调，执行初始化业务逻辑操作。

**模型约束**：此接口仅可在Stage模型下使用。

**系统能力**：SystemCapability.DistributedSched.AppCollaboration

**设备行为差异：** 该接口在不支持分布式业务的Wearable设备不生效。

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| want | Want | 是 | 当前Extension相关的Want信息，用于携带创建Extension所需的初始化配置信息。 |


**示例：**

```json
import { Want } from '@kit.AbilityKit';
import { DistributedExtensionAbility } from '@kit.DistributedServiceKit';

export default class DistributedExtension extends DistributedExtensionAbility {
  onCreate(want: Want) {
    console.info(`DistributedExtension Create ok`);
    console.info(`DistributedExtension on Create want: ${JSON.stringify(want)}`);
    console.info(`DistributedExtension Create end`);
  }
}
```



### onCollaborate


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

onCollaborate(wantParam: Record<string, Object>): AbilityConstant.CollaborateResult

Extension生命周期回调，在多设备限定协同场景下，协同方应用被拉起过程中返回是否接受协同的结果，返回结果决定协同流程是否继续。

**模型约束**：此接口仅可在Stage模型下使用。

**系统能力**：SystemCapability.DistributedSched.AppCollaboration

**设备行为差异：** 该接口在不支持分布式业务的Wearable设备不生效。

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| wantParam | Record<string, Object> | 是 | 协同回调参数，键值对对象，携带调用方传输的协同相关数据。开发者可通过"ohos.extra.param.key.supportCollaborateIndex"和"CollaborationValues"等key值获取这些数据，以决定是否接受协同请求及处理协同逻辑，影响协同流程是否继续。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| AbilityConstant.CollaborateResult | 表示协同方应用是否接受协同的结果。取值包括：ACCEPT表示接受协同，协同流程继续；REJECT表示拒绝协同，协同流程终止。 |


**示例**

```json
import { abilityConnectionManager, DistributedExtensionAbility } from '@kit.DistributedServiceKit';
import { AbilityConstant } from '@kit.AbilityKit';

export default class DistributedExtension extends DistributedExtensionAbility {
  onCollaborate(wantParam: Record<string, Object>) {
    console.info(`DistributedExtension onCollabRequest Accept to the result of Ability collaborate`);
    let sessionId = -1;
    const collaborationValues = wantParam["CollaborationValues"] as abilityConnectionManager.CollaborationValues;
    if (!collaborationValues) {
      console.error('Failed to get collaborationValues.');
      return sessionId;
    }
    console.info(`onCollab, collaborationValues: ${JSON.stringify(collaborationValues)}`);
    return AbilityConstant.CollaborateResult.ACCEPT;
  }
}
```



### onDestroy


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

onDestroy(): void

Extension生命周期回调，在销毁时回调，执行资源清理等操作。

**模型约束**：此接口仅可在Stage模型下使用。

**系统能力**：SystemCapability.DistributedSched.AppCollaboration

**设备行为差异：** 该接口在不支持分布式业务的Wearable设备不生效。

**示例：**

```text
import { DistributedExtensionAbility } from '@kit.DistributedServiceKit';

export default class DistributedExtension extends DistributedExtensionAbility {
  onDestroy() {
    console.info('DistributedExtension onDestroy ok');
  }
}
```



## 附录


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

DistributedExtensionAbility不支持以下模块的引用。


| Kit | 模块 |
| --- | --- |
| Ability Kit（程序框架服务） | @ohos.ability.featureAbility (FeatureAbility模块) |
| Ability Kit（程序框架服务） | @ohos.ability.particleAbility (ParticleAbility模块) |
| Ability Kit（程序框架服务） | UIAbilityContext |
| Ability Kit（程序框架服务） | @ohos.continuation.continuationManager (流转/协同管理) |
| ArkUI（方舟UI框架） | @ohos.prompt (弹窗) |
| ArkUI（方舟UI框架） | @ohos.promptAction (弹窗) |
| ArkUI（方舟UI框架） | @ohos.screenshot (屏幕截图) |
| Background Tasks Kit（后台任务开发服务） | @ohos.reminderAgent (后台代理提醒) |
| Background Tasks Kit（后台任务开发服务） | @ohos.reminderAgentManager (后台代理提醒) |
| Basic Services Kit（基础服务） | @ohos.account.appAccount (应用账号管理) |
| Basic Services Kit（基础服务） | @ohos.account.distributedAccount (分布式账号管理) |
| Basic Services Kit（基础服务） | @ohos.account.osAccount (系统账号管理) |
| Basic Services Kit（基础服务） | @ohos.power (系统电源管理) |
| Basic Services Kit（基础服务） | @ohos.wallpaper (壁纸) |
| Camera Kit（相机服务） | @ohos.multimedia.cameraPicker (相机选择器) |
| Connectivity Kit（短距通信服务） | @ohos.connectedTag (有源标签) |
| Connectivity Kit（短距通信服务） | nfctech (标准NFC-Tag Nfc 技术) |
| Connectivity Kit（短距通信服务） | @ohos.nfc.cardEmulation (标准NFC-cardEmulation) |
| Connectivity Kit（短距通信服务） | @ohos.nfc.controller (标准NFC) |
| Connectivity Kit（短距通信服务） | @ohos.nfc.tag (标准NFC-Tag) |
| Connectivity Kit（短距通信服务） | tagSession (标准NFC-Tag TagSession) |
| Contacts Kit（联系人服务） | @ohos.contact (联系人) |
| Core File Kit（文件基础服务） | @ohos.file.picker (选择器) |
| Form Kit（卡片开发服务） | @ohos.app.form.formBindingData (卡片数据绑定类) |
| Form Kit（卡片开发服务） | @ohos.app.form.FormExtensionAbility (FormExtensionAbility) |
| Form Kit（卡片开发服务） | @ohos.app.form.formInfo (formInfo) |
| Form Kit（卡片开发服务） | @ohos.app.form.formProvider (formProvider) |
| Form Kit（卡片开发服务） | @ohos.application.formError (formError) |
| Form Kit（卡片开发服务） | @ohos.application.formInfo (formInfo) |
| Form Kit（卡片开发服务） | @ohos.application.formProvider (formProvider) |
| IME Kit（输入法开发服务） | @ohos.inputMethod (输入法框架) |
| MultimediaKit | @ohos.multimedia.mediaLibrary (媒体库管理) |
| Media Library Kit（媒体文件管理服务） | @ohos.file.sendablePhotoAccessHelper (基于Sendable对象的相册管理模块) |
| Media Library Kit（媒体文件管理服务） | @ohos.file.AlbumPickerComponent (Album Picker组件) |
| Media Library Kit（媒体文件管理服务） | @ohos.file.PhotoPickerComponent (PhotoPicker组件) |
| Media Library Kit（媒体文件管理服务） | @ohos.file.RecentPhotoComponent (最近图片组件) |
| Media Library Kit（媒体文件管理服务） | @ohos.multimedia.movingphotoview (动态照片) |
| Notification Kit（用户通知服务） | @ohos.notification (Notification模块) |
| Notification Kit（用户通知服务） | @ohos.notificationManager (NotificationManager模块) |
| Sensor Service Kit（传感器服务） | @ohos.vibrator (振动) |
| Telephony Kit（蜂窝通信服务） | @ohos.telephony.call (拨打电话) |
| Telephony Kit（蜂窝通信服务） | @ohos.telephony.sim (SIM卡管理) |
| Telephony Kit（蜂窝通信服务） | @ohos.telephony.sms (短信服务) |
| User Authentication Kit（用户认证服务） | @ohos.userIAM.userAuth (用户认证) |
| Call Service Kit（通话服务） | voipCall (应用内通话管理) |
| Live View Kit（实况窗服务） | liveViewManager |
| Scan Kit（统一扫码服务） | customScan (自定义界面扫码) |
| Scan Kit（统一扫码服务） | generateBarcode (码图生成) |
| Scan Kit（统一扫码服务） | detectBarcode (图像识码) |
| Scan Kit（统一扫码服务） | scanBarcode (默认界面扫码) |
| Scan Kit（统一扫码服务） | scanCore (扫码公共信息) |
