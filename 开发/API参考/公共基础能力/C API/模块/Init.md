# Init

更新时间：2026-09-24 09:52:23

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/init
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

提供系统能力查询接口。
 
通过读取系统能力参数文件，返回指定的某个系统能力是否被支持。
 
**起始版本：** 8
 
  

## 文件汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| syscap_ndk.h | 查询单个系统能力是否被支持的API。 引用文件：<syscap_ndk.h> 库：libdeviceinfo_ndk.z.so |
 
 
  

### 函数


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| canIUse (const char *cap) | 查询指定的系统能力是否被支持。 系统能力（SystemCapability，简称SysCap），指操作系统中每一个相对独立的特性。不同的设备对应不同的系统能力集，每个系统能力对应一个或多个API。开发者可根据系统能力来判断是否可以使用某接口。 |
