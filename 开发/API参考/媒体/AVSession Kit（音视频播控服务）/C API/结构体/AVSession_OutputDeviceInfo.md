# AVSession_OutputDeviceInfo

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohavsession-avsession-outputdeviceinfo
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct AVSession_OutputDeviceInfo {...} AVSession_OutputDeviceInfo
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

输出设备信息的定义。
 
**起始版本：** 23
 
**相关模块：** [OHAVSession](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohavsession)
 
**所在头文件：** [native_deviceinfo.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-deviceinfo-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| uint32_t size | 设备信息数组的大小，表示deviceInfos数组的元素数量。 |
| AVSession_DeviceInfo **deviceInfos | 指向设备信息数组的指针，数组长度由size字段指定。 |
