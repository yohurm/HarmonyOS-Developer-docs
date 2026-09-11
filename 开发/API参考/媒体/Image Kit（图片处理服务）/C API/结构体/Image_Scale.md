# Image_Scale

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-image-nativemodule-image-scale
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct Image_Scale {...} Image_Scale
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

图像缩放倍数。
 
**起始版本：** 22
 
**相关模块：** [Image_NativeModule](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-image-nativemodule)
 
**所在头文件：** [image_common.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-image-common-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| float x | 宽度的缩放倍数。 取值不能为0，建议取正数，否则会产生翻转效果。 |
| float y | 高度的缩放倍数。 取值不能为0，建议取正数，否则会产生翻转效果。 |
