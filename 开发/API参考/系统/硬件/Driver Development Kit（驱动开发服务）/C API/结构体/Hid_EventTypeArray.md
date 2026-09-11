# Hid_EventTypeArray

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-hidddk-hid-eventtypearray
**支持设备：** PC/2in1

```text
typedef struct Hid_EventTypeArray {...} Hid_EventTypeArray
```
  

## 概述


**支持设备：** PC/2in1

事件类型编码数组，用于存储HID设备支持的事件类型信息。
 
**起始版本：** 11
 
**相关模块：** [HidDdk](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-hidddk)
 
**所在头文件：** [hid_ddk_types.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-hid-ddk-types-h)
 
  

## 汇总


**支持设备：** PC/2in1

  

### 成员变量


**支持设备：** PC/2in1
 

| 名称 | 描述 |
| --- | --- |
| Hid_EventType* hidEventType | 事件类型编码数组的指针，指向调用方预先分配的数组（不允许为空指针），数组大小不小于length。 |
| uint16_t length | 数组的有效长度，不超过hidEventType数组的实际长度。 |
