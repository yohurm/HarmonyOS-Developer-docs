# OH_ArkUI_ImageAttachment

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-arkui-nativemodule-oh-arkui-imageattachment
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct OH_ArkUI_ImageAttachment OH_ArkUI_ImageAttachment
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

定义图片对象，用于在属性字符串中嵌入图片内容。图片作为属性字符串的组成部分，通过设置图片源及样式属性后，可附加到属性字符串中实现图文混排。
 
调用[OH_ArkUI_ImageAttachment_Create](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h#oh_arkui_imageattachment_create)接口创建图片样式对象。
 
调用[OH_ArkUI_ImageAttachment_Destroy](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h#oh_arkui_imageattachment_destroy)接口销毁图片样式对象。
 
对象创建后，调用OH_ArkUI_ImageAttachment_SetXXX系列接口设置样式属性。例如调用[OH_ArkUI_ImageAttachment_SetPixelMap](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h#oh_arkui_imageattachment_setpixelmap)设置图片源。
 
**起始版本：** 24
 
**相关模块：** [ArkUI_NativeModule](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-arkui-nativemodule)
 
**所在头文件：** [styled_string.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h)
