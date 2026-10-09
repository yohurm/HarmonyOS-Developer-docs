# OH_ArkUI_BaselineOffsetStyle

更新时间：2026-08-29 09:41:17（官网已下线）

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-arkui-nativemodule-oh-arkui-baselineoffsetstyle
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct OH_ArkUI_BaselineOffsetStyle OH_ArkUI_BaselineOffsetStyle
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

定义基线偏移量样式，用于在属性字符串中设置文本的基线偏移量，使文本在垂直方向上相对于基线进行上移或下移，从而实现上下标等特殊排版效果。基线偏移量样式需通过创建样式对象、设置偏移值后应用到属性字符串中生效。
 
调用[OH_ArkUI_BaselineOffsetStyle_Create](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h#oh_arkui_baselineoffsetstyle_create)接口创建基线偏移量样式对象。
 
对象创建后，调用[OH_ArkUI_BaselineOffsetStyle_SetBaselineOffset](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h#oh_arkui_baselineoffsetstyle_setbaselineoffset)接口设置基线偏移量值。
 
调用[OH_ArkUI_BaselineOffsetStyle_GetBaselineOffset](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h#oh_arkui_baselineoffsetstyle_getbaselineoffset)接口获取基线偏移量值。
 
使用完毕后，调用[OH_ArkUI_BaselineOffsetStyle_Destroy](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h#oh_arkui_baselineoffsetstyle_destroy)接口销毁基线偏移量样式对象。
 
**起始版本：** 24
 
**相关模块：** [ArkUI_NativeModule](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-arkui-nativemodule)
 
**所在头文件：** [styled_string.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h)
