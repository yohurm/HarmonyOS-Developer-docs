# native_deviceinfo.h

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-deviceinfo-h
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

提供播控设备信息的定义。
 
**引用文件：** <multimedia/av_session/native_deviceinfo.h>
 
**库：** libohavsession.so
 
**系统能力：** SystemCapability.Multimedia.AVSession.Core
 
**起始版本：** 23
 
**相关模块：** [OHAVSession](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohavsession)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 结构体


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | typedef关键字 | 描述 |
| --- | --- | --- |
| AVSession_OutputDeviceInfo | AVSession_OutputDeviceInfo | 目标设备信息的定义。 |
| AVSession_DeviceInfo | AVSession_DeviceInfo | 设备信息的声明。该实例用于获取更多的设备信息及其详细属性。 |
 
 
  

### 函数


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| AVSession_ErrCode OH_DeviceInfo_GetAVCastCategory(AVSession_DeviceInfo *deviceInfo, AVSession_AVCastCategory *aVCastCategory) | 获取目标设备的投播类别。 |
| AVSession_ErrCode OH_DeviceInfo_GetDeviceId(AVSession_DeviceInfo *deviceInfo, char **deviceId) | 获取目标设备的设备ID。 |
| AVSession_ErrCode OH_DeviceInfo_GetDeviceName(AVSession_DeviceInfo *deviceInfo, char **deviceName) | 获取目标设备的设备名称。 |
| AVSession_ErrCode OH_DeviceInfo_GetDeviceType(AVSession_DeviceInfo *deviceInfo, AVSession_DeviceType *deviceType) | 获取目标设备的设备类型。 |
| AVSession_ErrCode OH_DeviceInfo_GetSupportedProtocols(AVSession_DeviceInfo *deviceInfo, uint32_t *deviceProtocolType) | 获取目标设备支持的协议。 |
 
 
  

## 函数说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### OH_DeviceInfo_GetAVCastCategory()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
AVSession_ErrCode OH_DeviceInfo_GetAVCastCategory(AVSession_DeviceInfo *deviceInfo, AVSession_AVCastCategory *aVCastCategory)
```
 
**描述**
 
获取目标设备的投播类别。
 
**起始版本：** 23
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| AVSession_DeviceInfo *deviceInfo | 表示设备信息实例指针。 |
| AVSession_AVCastCategory *aVCastCategory | 输出参数，用于接收投播类别的指针变量。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| AVSession_ErrCode | AV_SESSION_ERR_SUCCESS：函数执行成功。 AV_SESSION_ERR_INVALID_PARAMETER： 1. 参数deviceInfo为nullptr。 2. 参数aVCastCategory为nullptr。 |
 
 
  

### OH_DeviceInfo_GetDeviceId()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
AVSession_ErrCode OH_DeviceInfo_GetDeviceId(AVSession_DeviceInfo *deviceInfo, char **deviceId)
```
 
**描述**
 
获取目标设备的设备ID。
 
**起始版本：** 23
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| AVSession_DeviceInfo *deviceInfo | 表示设备信息实例指针。 |
| char **deviceId | 输出参数，用于存储获取到的设备ID字符串指针。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| AVSession_ErrCode | AV_SESSION_ERR_SUCCESS：函数执行成功。 AV_SESSION_ERR_INVALID_PARAMETER： 1. 参数deviceInfo为nullptr。 2. 参数deviceId为nullptr。 |
 
 
  

### OH_DeviceInfo_GetDeviceName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
AVSession_ErrCode OH_DeviceInfo_GetDeviceName(AVSession_DeviceInfo *deviceInfo, char **deviceName)
```
 
**描述**
 
获取目标设备的设备名称。
 
**起始版本：** 23
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| AVSession_DeviceInfo *deviceInfo | 表示设备信息实例指针。 |
| char **deviceName | 输出参数，用于存储获取到的设备名称字符串指针。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| AVSession_ErrCode | AV_SESSION_ERR_SUCCESS：函数执行成功。 AV_SESSION_ERR_INVALID_PARAMETER： 1. 参数deviceInfo为nullptr。 2. 参数deviceName为nullptr。 |
 
 
  

### OH_DeviceInfo_GetDeviceType()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
AVSession_ErrCode OH_DeviceInfo_GetDeviceType(AVSession_DeviceInfo *deviceInfo, AVSession_DeviceType *deviceType)
```
 
**描述**
 
获取目标设备的设备类型。
 
**起始版本：** 23
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| AVSession_DeviceInfo *deviceInfo | 表示设备信息实例指针。 |
| AVSession_DeviceType *deviceType | 输出参数，用于接收设备类型的指针，具体枚举值含义见AVSession_DeviceType。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| AVSession_ErrCode | AV_SESSION_ERR_SUCCESS：函数执行成功。 AV_SESSION_ERR_INVALID_PARAMETER： 1. 参数deviceInfo为nullptr。 2. 参数deviceType为nullptr。 |
 
 
  

### OH_DeviceInfo_GetSupportedProtocols()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
AVSession_ErrCode OH_DeviceInfo_GetSupportedProtocols(AVSession_DeviceInfo *deviceInfo, uint32_t *deviceProtocolType)
```
 
**描述**
 
获取目标设备支持的协议。
 
**起始版本：** 23
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| AVSession_DeviceInfo *deviceInfo | 表示设备信息实例指针。 |
| uint32_t *deviceProtocolType | 输出参数，用于接收设备支持的协议类型的指针，返回值为协议类型的位掩码组合。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| AVSession_ErrCode | AV_SESSION_ERR_SUCCESS：函数执行成功。 AV_SESSION_ERR_INVALID_PARAMETER： 1. 参数deviceInfo为nullptr。 2. 参数deviceProtocolType为nullptr。 |
