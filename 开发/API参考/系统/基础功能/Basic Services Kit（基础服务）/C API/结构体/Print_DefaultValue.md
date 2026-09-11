# Print_DefaultValue

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-oh-print-print-defaultvalue
**支持设备：** Phone | PC/2in1 | Tablet

```text
typedef struct {...} Print_DefaultValue
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet

表示打印机的默认属性值，包含色彩模式、双面模式、介质类型、纸张尺寸、边距、纸张来源、打印质量、份数、分辨率、方向等默认打印参数。
 
**起始版本：** 12
 
**相关模块：** [OH_Print](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-oh-print)
 
**所在头文件：** [ohprint.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohprint-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet
 

| 名称 | 描述 |
| --- | --- |
| Print_ColorMode defaultColorMode | 默认色彩模式，表示打印输出的色彩方式，具体取值由打印机支持的色彩模式决定。 |
| Print_DuplexMode defaultDuplexMode | 默认双面模式，表示打印的单双面方式，具体取值由打印机支持的双面模式决定。 |
| char *defaultMediaType | 默认介质类型，表示打印所使用的介质类型（如普通纸、光面纸等），具体取值由打印机支持的介质类型决定。 |
| char *defaultPageSizeId | 默认纸张尺寸 ID，表示打印所使用的纸张尺寸标识（如"A4"、"Letter"等），具体取值由打印机支持的纸张尺寸决定。 |
| Print_Margin defaultMargin | 默认边距，表示打印输出页面的边距设置，具体取值由打印机支持的边距决定。 |
| char *defaultPaperSource | 默认纸张来源，表示打印所使用的纸张来源（如自动进纸器、手动进纸等），具体取值由打印机支持的纸张来源决定。 |
| Print_Quality defaultPrintQuality | 默认打印质量，表示打印输出的质量等级设置，具体取值由打印机支持的打印质量决定。 |
| uint32_t defaultCopies | 默认份数，取值原则：不小于 1。 |
| Print_Resolution defaultResolution | 默认分辨率，表示打印输出的分辨率，具体取值由打印机支持的分辨率决定。 |
| Print_OrientationMode defaultOrientation | 默认打印方向，表示打印内容的方向模式（如纵向、横向等），具体取值由打印机支持的打印方向决定。 |
| char *otherDefaultValues | JSON 格式的其他默认值，用于表示未在上述成员变量中单独列出的额外打印默认属性，具体可设置的键值对由打印机支持的扩展能力决定。 |
