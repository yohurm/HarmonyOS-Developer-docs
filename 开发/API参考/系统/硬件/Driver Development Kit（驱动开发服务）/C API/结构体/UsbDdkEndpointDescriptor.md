# UsbDdkEndpointDescriptor

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-usbddk-usbddkendpointdescriptor
**支持设备：** PC/2in1

```text
typedef struct UsbDdkEndpointDescriptor {...} UsbDdkEndpointDescriptor
```
  

## 概述


**支持设备：** PC/2in1

端点描述符，包含标准端点描述符和未做解析的描述符信息。
 
**起始版本：** 10
 
**相关模块：** [UsbDdk](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-usbddk)
 
**所在头文件：** [usb_ddk_types.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-usb-ddk-types-h)
 
  

## 汇总


**支持设备：** PC/2in1

  

### 成员变量


**支持设备：** PC/2in1
 

| 名称 | 描述 |
| --- | --- |
| struct UsbEndpointDescriptor endpointDescriptor | 标准端点描述符。 |
| const uint8_t* extra | 未做解析的描述符指针，包含特定于类或供应商的描述符。 |
| uint32_t extraLength | 未做解析的描述符长度。 |
