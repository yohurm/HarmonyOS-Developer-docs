# UsbDdkInterface

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-usbddk-usbddkinterface
**支持设备：** PC/2in1

```text
typedef struct UsbDdkInterface {...} UsbDdkInterface
```
  

## 概述


**支持设备：** PC/2in1

USB接口，是特定接口下备用设置的集合。
 
**起始版本：** 10
 
**相关模块：** [UsbDdk](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-usbddk)
 
**所在头文件：** [usb_ddk_types.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-usb-ddk-types-h)
 
  

## 汇总


**支持设备：** PC/2in1

  

### 成员变量


**支持设备：** PC/2in1
 

| 名称 | 描述 |
| --- | --- |
| uint8_t numAltsetting | USB接口的备用设置数量。 |
| struct UsbDdkInterfaceDescriptor* altsetting | USB接口的备用设置数组的指针，数组的长度由numAltsetting指定。 |
