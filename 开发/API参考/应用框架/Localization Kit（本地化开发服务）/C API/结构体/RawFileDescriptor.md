# RawFileDescriptor

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-rawfile-rawfiledescriptor
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct {...} RawFileDescriptor
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

提供rawfile文件描述符信息，包含rawfile的文件描述符、在HAP包中的起始位置和文件长度。
 
通过[OH_ResourceManager_GetRawFileDescriptorData](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-raw-file-h#oh_resourcemanager_getrawfiledescriptordata)获取，使用完后须调用[OH_ResourceManager_ReleaseRawFileDescriptorData](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-raw-file-h#oh_resourcemanager_releaserawfiledescriptordata)释放文件描述符资源。
 
**起始版本：** 8
 
**相关模块：** [rawfile](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-rawfile)
 
**所在头文件：** [raw_file.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-raw-file-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| int fd | rawfile文件描述符。 |
| long start | rawfile文件在HAP包中的起始位置，单位为Byte。 |
| long length | rawfile文件的长度，单位为Byte。 |
