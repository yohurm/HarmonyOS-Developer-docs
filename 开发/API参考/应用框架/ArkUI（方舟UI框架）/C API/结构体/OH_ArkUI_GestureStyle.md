# OH_ArkUI_GestureStyle

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-arkui-nativemodule-oh-arkui-gesturestyle
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct OH_ArkUI_GestureStyle OH_ArkUI_GestureStyle
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

定义手势样式，适用于需要配置手势样式并接收相关事件回调的场景，便于应用统一管理手势样式及事件回调。 
 
调用[OH_ArkUI_GestureStyle_Create](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h#oh_arkui_gesturestyle_create)接口创建对应的手势样式对象。
 
对象创建后调用OH_ArkUI_GestureStyle_RegisterOnXXXCallback系列接口注册具体的事件回调，例如调用[OH_ArkUI_GestureStyle_RegisterOnClickCallback](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h#oh_arkui_gesturestyle_registeronclickcallback)注册点击事件回调。
 
使用完毕后，调用[OH_ArkUI_GestureStyle_Destroy](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h#oh_arkui_gesturestyle_destroy)接口销毁手势样式对象。
 
**起始版本：** 24
 
**相关模块：** [ArkUI_NativeModule](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-arkui-nativemodule)
 
**所在头文件：** [styled_string.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h)
