# Hid_AbsAxesArray

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-hidddk-hid-absaxesarray
**支持设备：** PC/2in1

```text
typedef struct Hid_AbsAxesArray {...} Hid_AbsAxesArray
```
  

## 概述


**支持设备：** PC/2in1

绝对坐标属性数组，用于存储HID设备的多个绝对坐标轴的属性信息，支持描述如触摸屏、游戏摇杆等输入设备的坐标特征，适用于需要精确读取和处理多维输入数据的驱动开发场景，例如在手柄、触摸板等输入设备中记录轴位数据。
 
**起始版本：** 11
 
**相关模块：** [HidDdk](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-hidddk)
 
**所在头文件：** [hid_ddk_types.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-hid-ddk-types-h)
 
  

## 汇总


**支持设备：** PC/2in1

  

### 成员变量


**支持设备：** PC/2in1
 

| 名称 | 描述 |
| --- | --- |
| Hid_AbsAxes* hidAbsAxes | 指向绝对坐标属性编码数组首元素的指针。需与length配合使用，指针需有效且不为 NULL。 |
| uint16_t length | 数组的有效长度，表示hidAbsAxes指针指向的有效元素个数。取值范围：[0, 65535]。 |
