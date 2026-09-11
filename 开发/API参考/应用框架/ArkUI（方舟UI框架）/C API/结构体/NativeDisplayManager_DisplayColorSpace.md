# NativeDisplayManager_DisplayColorSpace

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-nativedisplaymanager-displaycolorspace
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct {...} NativeDisplayManager_DisplayColorSpace
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

显示设备支持的色域类型信息。
 
**起始版本：** 14
 
**相关模块：** [OH_DisplayManager](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-oh-displaymanager)
 
**所在头文件：** [oh_display_info.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-oh-display-info-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| uint32_t colorSpaceLength | 显示设备支持的色域类型数量。 |
| uint32_t* colorSpaces | 指向显示设备支持的色域类型数组的指针。 |
