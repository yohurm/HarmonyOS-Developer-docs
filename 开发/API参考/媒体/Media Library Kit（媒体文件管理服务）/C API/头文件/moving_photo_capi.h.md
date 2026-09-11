# moving_photo_capi.h

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-moving-photo-capi-h
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

定义与动态照片相关的API。提供获取动态照片信息的功能。
 
**库：** libmedia_asset_manager.so
 
**引用文件：** <multimedia/media_library/moving_photo_capi.h>
 
**系统能力：** SystemCapability.FileManagement.PhotoAccessHelper.Core
 
**起始版本：** 13
 
**相关模块：** [MediaAssetManager](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-mediaassetmanager)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 函数


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| MediaLibrary_ErrorCode OH_MovingPhoto_GetUri(OH_MovingPhoto* movingPhoto, const char** uri) | 获取动态照片的uri。 |
| MediaLibrary_ErrorCode OH_MovingPhoto_RequestContentWithUris(OH_MovingPhoto* movingPhoto, char* imageUri, char* videoUri) | 同时请求动态照片的图片内容和视频内容，并写入参数指定的URI中。 |
| MediaLibrary_ErrorCode OH_MovingPhoto_RequestContentWithUri(OH_MovingPhoto* movingPhoto, MediaLibrary_ResourceType resourceType, char* uri) | 请求指定资源类型的动态照片内容，并写入参数指定的uri中。 |
| MediaLibrary_ErrorCode OH_MovingPhoto_RequestContentWithBuffer(OH_MovingPhoto* movingPhoto, MediaLibrary_ResourceType resourceType, const uint8_t** buffer, uint32_t* size) | 请求指定资源类型的动态照片内容，以ArrayBuffer的形式返回。 |
| MediaLibrary_ErrorCode OH_MovingPhoto_Release(OH_MovingPhoto* movingPhoto) | 释放OH_MovingPhoto实例。 |
 
 
  

## 函数说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### OH_MovingPhoto_GetUri()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
MediaLibrary_ErrorCode OH_MovingPhoto_GetUri(OH_MovingPhoto* movingPhoto, const char** uri)
```
 
**描述**
 
获取动态照片的uri。
 
**起始版本：** 13
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| OH_MovingPhoto* movingPhoto | OH_MovingPhoto实例。 |
| const char** uri | 指向动态照片对象标识URI的指针。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| MediaLibrary_ErrorCode | MEDIA_LIBRARY_OK：方法调用成功。 MEDIA_LIBRARY_PARAMETER_ERROR：参数错误。可能的原因： 1. 未指定强制参数。 2. 参数类型不正确。 3. 参数验证失败。 MEDIA_LIBRARY_INTERNAL_SYSTEM_ERROR：内部系统错误。 |
 
 
  

### OH_MovingPhoto_RequestContentWithUris()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
MediaLibrary_ErrorCode OH_MovingPhoto_RequestContentWithUris(OH_MovingPhoto* movingPhoto, char* imageUri,char* videoUri)
```
 
**描述**
 
同时请求动态照片的图片内容和视频内容，并写入参数指定的URI中。
 
**需要权限：** ohos.permission.READ_IMAGEVIDEO
 
**起始版本：** 13
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| OH_MovingPhoto* movingPhoto | OH_MovingPhoto实例。 |
| char* imageUri | 保存图像数据的目标文件URI。 |
| char* videoUri | 保存视频数据的目标文件URI。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| MediaLibrary_ErrorCode | MEDIA_LIBRARY_OK：方法调用成功。 MEDIA_LIBRARY_PARAMETER_ERROR：参数错误。可能的原因： 1. 未指定强制参数。 2. 参数类型不正确。 3. 参数验证失败。 MEDIA_LIBRARY_PERMISSION_DENIED：没有权限。 MEDIA_LIBRARY_INTERNAL_SYSTEM_ERROR：内部系统错误。 |
 
 
  

### OH_MovingPhoto_RequestContentWithUri()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
MediaLibrary_ErrorCode OH_MovingPhoto_RequestContentWithUri(OH_MovingPhoto* movingPhoto,MediaLibrary_ResourceType resourceType, char* uri)
```
 
**描述**
 
请求指定资源类型的动态照片内容，并将内容写入指定URI。
 
**需要权限：** ohos.permission.READ_IMAGEVIDEO
 
**起始版本：** 13
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| OH_MovingPhoto* movingPhoto | OH_MovingPhoto实例。 |
| MediaLibrary_ResourceType resourceType | 指定的资源类型MediaLibrary_ResourceType。 |
| char* uri | 保存数据的目标文件uri。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| MediaLibrary_ErrorCode | MEDIA_LIBRARY_OK：方法调用成功。 MEDIA_LIBRARY_PARAMETER_ERROR：参数错误。可能的原因： 1. 未指定强制参数。 2. 参数类型不正确。 3. 参数验证失败。 MEDIA_LIBRARY_PERMISSION_DENIED：没有权限。 MEDIA_LIBRARY_INTERNAL_SYSTEM_ERROR：内部系统错误。 |
 
 
  

### OH_MovingPhoto_RequestContentWithBuffer()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
MediaLibrary_ErrorCode OH_MovingPhoto_RequestContentWithBuffer(OH_MovingPhoto* movingPhoto,MediaLibrary_ResourceType resourceType, const uint8_t** buffer, uint32_t* size)
```
 
**描述**
 
请求指定资源类型的动态照片内容，以ArrayBuffer的形式返回。
 
**需要权限：** ohos.permission.READ_IMAGEVIDEO
 
**起始版本：** 13
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| OH_MovingPhoto* movingPhoto | OH_MovingPhoto实例。 |
| MediaLibrary_ResourceType resourceType | 指定的资源类型MediaLibrary_ResourceType。 |
| const uint8_t** buffer | 指向保存目标文件数据缓冲区的指针，用于接收请求的资源内容数据。 |
| uint32_t* size | 输出参数，返回缓冲区数据的大小，单位：字节（Byte）。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| MediaLibrary_ErrorCode | MEDIA_LIBRARY_OK：方法调用成功。 MEDIA_LIBRARY_PARAMETER_ERROR：参数错误。可能的原因： 1. 未指定强制参数。 2. 参数类型不正确。 3. 参数验证失败。 MEDIA_LIBRARY_PERMISSION_DENIED：没有权限。 MEDIA_LIBRARY_INTERNAL_SYSTEM_ERROR：内部系统错误。 |
 
 
  

### OH_MovingPhoto_Release()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
MediaLibrary_ErrorCode OH_MovingPhoto_Release(OH_MovingPhoto* movingPhoto)
```
 
**描述**
 
释放[OH_MovingPhoto](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-mediaassetmanager-oh-movingphoto)实例。
 
**起始版本：** 13
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| OH_MovingPhoto* movingPhoto | 要释放的OH_MovingPhoto实例。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| MediaLibrary_ErrorCode | MEDIA_LIBRARY_OK：方法调用成功。 MEDIA_LIBRARY_PARAMETER_ERROR：参数错误。可能的原因： 1. 未指定强制参数。 2. 参数类型不正确。 3. 参数验证失败。 |
