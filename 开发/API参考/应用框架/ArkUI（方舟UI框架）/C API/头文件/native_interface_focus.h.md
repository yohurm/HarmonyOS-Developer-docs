# native_interface_focus.h

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-interface-focus-h
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

定义焦点管理的相关接口，主要用于主动转移焦点、管理控制焦点转移默认行为，以及控制焦点激活态，适用于页面切换、键盘导航等需要统一管理焦点状态和焦点转移行为的场景，有助于提升焦点控制的可预测性和交互体验。
 
**引用文件：** <arkui/native_interface_focus.h>
 
**库：** libace_ndk.z.so
 
**系统能力：** SystemCapability.ArkUI.ArkUI.Full
 
**起始版本：** 15
 
**相关模块：** [ArkUI_NativeModule](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-arkui-nativemodule)
 
**相关示例：** [NdkFocus](https://gitcode.com/HarmonyOS_Samples/guide-snippets/tree/master/ArkUISample/NdkFocus)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 枚举


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | typedef关键字 | 描述 |
| --- | --- | --- |
| ArkUI_KeyProcessingMode | ArkUI_KeyProcessingMode | 按键事件的处理模式。 |
 
 
  

### 函数


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| ArkUI_ErrorCode OH_ArkUI_FocusRequest(ArkUI_NodeHandle node) | 为特定节点请求焦点。 |
| void OH_ArkUI_FocusClear(ArkUI_ContextHandle uiContext) | 将当前焦点清除到根容器节点。 |
| void OH_ArkUI_FocusActivate(ArkUI_ContextHandle uiContext, bool isActive, bool isAutoInactive) | 设置当前界面的焦点激活态，获焦节点显示焦点框。 |
| void OH_ArkUI_FocusSetAutoTransfer(ArkUI_ContextHandle uiContext, bool autoTransfer) | 设置页面切换时焦点是否自动转移。 |
| void OH_ArkUI_FocusSetKeyProcessingMode(ArkUI_ContextHandle uiContext, ArkUI_KeyProcessingMode mode) | 设置按键事件处理的优先级。 |
 
 
  

## 枚举类型说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### ArkUI_KeyProcessingMode


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
enum ArkUI_KeyProcessingMode
```
 
**描述：**
 
按键事件的处理模式。
 
**起始版本：** 15
  

| 枚举项 | 描述 |
| --- | --- |
| ARKUI_KEY_PROCESSING_MODE_FOCUS_NAVIGATION = 0 | 按键事件用于移动焦点。 |
| ARKUI_KEY_PROCESSING_MODE_FOCUS_ANCESTOR_EVENT = 1 | 按键事件向上传递给祖先组件。 |
 
 
  

## 函数说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### OH_ArkUI_FocusRequest()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ArkUI_ErrorCode OH_ArkUI_FocusRequest(ArkUI_NodeHandle node)
```
 
**描述：**
 
为特定节点请求焦点，适用于需要主动将焦点移动到指定组件的场景，例如页面初始化后设置默认焦点或通过键盘、遥控器进行焦点导航。
 
**起始版本：** 15
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| ArkUI_NodeHandle node | 需要请求焦点的节点。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ArkUI_ErrorCode | 错误码。 ARKUI_ERROR_CODE_NO_ERROR 请求成功。 ARKUI_ERROR_CODE_FOCUS_NON_FOCUSABLE 节点无法获得焦点。 ARKUI_ERROR_CODE_FOCUS_NON_FOCUSABLE_ANCESTOR 祖先节点无法获得焦点。 ARKUI_ERROR_CODE_FOCUS_NON_EXISTENT 节点不存在。 |
 
 
  

### OH_ArkUI_FocusClear()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
void OH_ArkUI_FocusClear(ArkUI_ContextHandle uiContext)
```
 
**描述：**
 
将当前焦点清除到根容器节点，适用于退出当前焦点交互或需要重置页面焦点状态的场景。
 
**起始版本：** 15
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| ArkUI_ContextHandle uiContext | 需要清除焦点的UI实例对象的指针。 |
 
 
  

### OH_ArkUI_FocusActivate()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
void OH_ArkUI_FocusActivate(ArkUI_ContextHandle uiContext, bool isActive, bool isAutoInactive)
```
 
**描述：**
 
设置当前界面的焦点激活态，获焦节点显示焦点框，适用于需要在键盘、遥控器等非触摸交互中显示焦点位置的场景。
 
**起始版本：** 15
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| ArkUI_ContextHandle uiContext | UI实例对象指针。 |
| bool isActive | 设置是否进入/退出焦点激活态。true表示进入焦点激活态，false表示退出焦点激活态。 |
| bool isAutoInactive | 当触摸事件或鼠标按下事件触发时，true表示将状态设置为退出焦点激活态，false表示在再次调用OH_ArkUI_FocusActivate设置焦点激活态前，保持当前状态。 |
 
 
  

### OH_ArkUI_FocusSetAutoTransfer()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
void OH_ArkUI_FocusSetAutoTransfer(ArkUI_ContextHandle uiContext, bool autoTransfer)
```
 
**描述：**
 
设置页面切换时焦点是否自动转移。
 
**起始版本：** 15
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| ArkUI_ContextHandle uiContext | UI实例对象指针。 |
| bool autoTransfer | 页面切换时，是否转移焦点。true表示页面切换时自动转移焦点到新页面；false表示页面切换时焦点不转移。 |
 
 
  

### OH_ArkUI_FocusSetKeyProcessingMode()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
void OH_ArkUI_FocusSetKeyProcessingMode(ArkUI_ContextHandle uiContext, ArkUI_KeyProcessingMode mode)
```
 
**描述：**
 
设置按键事件处理的优先级，适用于需要在焦点导航和祖先组件按键事件处理之间选择优先策略的场景。
 
**起始版本：** 15
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| ArkUI_ContextHandle uiContext | UI实例对象指针。 |
| ArkUI_KeyProcessingMode mode | 按键事件处理的优先级。 |
