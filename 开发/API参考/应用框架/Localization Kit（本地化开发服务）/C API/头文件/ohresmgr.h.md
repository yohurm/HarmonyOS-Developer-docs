# ohresmgr.h

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohresmgr-h
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

提供资源管理Native层获取资源的能力。
 
**引用文件：** <resourcemanager/ohresmgr.h>
 
**库：** libohresmgr.so
 
**系统能力：** SystemCapability.Global.ResourceManager
 
**起始版本：** 12
 
**相关模块：** [resourcemanager](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-resourcemanager)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 函数


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| ResourceManager_ErrorCode OH_ResourceManager_GetMediaBase64(const NativeResourceManager *mgr, uint32_t resId, char **resultValue, uint64_t *resultLen, uint32_t density = 0) | 通过指定资源ID和屏幕密度，获取对应的media资源的Base64编码字符串。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetMediaBase64Data(const NativeResourceManager *mgr, uint32_t resId, char **resultValue, uint64_t *resultLen, uint32_t density) | 通过指定资源ID和屏幕密度，获取对应的media资源的Base64编码字符串。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetMediaBase64ByName(const NativeResourceManager *mgr, const char *resName, char **resultValue, uint64_t *resultLen, uint32_t density = 0) | 通过指定资源名称和屏幕密度，获取对应的media资源的Base64编码字符串。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetMediaBase64DataByName(const NativeResourceManager *mgr, const char *resName, char **resultValue, uint64_t *resultLen, uint32_t density) | 通过指定资源名称和屏幕密度，获取对应的media资源的Base64编码字符串。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetMedia(const NativeResourceManager *mgr, uint32_t resId, uint8_t **resultValue, uint64_t *resultLen, uint32_t density = 0) | 通过指定资源ID和屏幕密度，获取对应的media资源的二进制数据。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetMediaData(const NativeResourceManager *mgr, uint32_t resId, uint8_t **resultValue, uint64_t *resultLen, uint32_t density) | 通过指定资源ID和屏幕密度，获取对应的media资源的二进制数据。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetMediaByName(const NativeResourceManager *mgr, const char *resName, uint8_t **resultValue, uint64_t *resultLen, uint32_t density = 0) | 通过指定资源名称和屏幕密度，获取对应的media资源的二进制数据。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetMediaDataByName(const NativeResourceManager *mgr, const char *resName, uint8_t **resultValue, uint64_t *resultLen, uint32_t density) | 通过指定资源名称和屏幕密度，获取对应的media资源的二进制数据。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetDrawableDescriptor(const NativeResourceManager *mgr, uint32_t resId, ArkUI_DrawableDescriptor **drawableDescriptor, uint32_t density = 0, uint32_t type = 0) | 通过指定资源ID、屏幕密度、图标类型，获取图标资源对应的DrawableDescriptor对象。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetDrawableDescriptorData(const NativeResourceManager *mgr, uint32_t resId, ArkUI_DrawableDescriptor **drawableDescriptor, uint32_t density, uint32_t type) | 通过指定资源ID、屏幕密度、图标类型，获取图标资源对应的DrawableDescriptor对象。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetDrawableDescriptorByName(const NativeResourceManager *mgr, const char *resName, ArkUI_DrawableDescriptor **drawableDescriptor, uint32_t density = 0, uint32_t type = 0) | 通过指定资源名称、屏幕密度、图标类型，获取图标资源对应的DrawableDescriptor对象。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetDrawableDescriptorDataByName(const NativeResourceManager *mgr, const char *resName, ArkUI_DrawableDescriptor **drawableDescriptor, uint32_t density, uint32_t type) | 通过指定资源名称和屏幕密度，获取对应的图标资源的DrawableDescriptor对象。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetSymbol(const NativeResourceManager *mgr, uint32_t resId, uint32_t *resultValue) | 获取指定资源ID对应的Symbol图标的Unicode编码。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetSymbolByName(const NativeResourceManager *mgr, const char *resName, uint32_t *resultValue) | 获取指定资源名称对应的Symbol图标的Unicode编码。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetLocales(const NativeResourceManager *mgr, char ***resultValue, uint32_t *resultLen, bool includeSystem = false) | 获取应用支持的语言列表。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetLocalesData(const NativeResourceManager *mgr, char ***resultValue, uint32_t *resultLen, bool includeSystem) | 获取应用支持的语言列表。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetConfiguration(const NativeResourceManager *mgr, ResourceManager_Configuration *configuration) | 获取设备的屏幕方向、语言区域、设备类型、屏幕密度、颜色模式等配置信息。(API20废弃) |
| ResourceManager_ErrorCode OH_ResourceManager_GetResourceConfiguration(const NativeResourceManager *mgr, ResourceManager_Configuration *configuration) | 获取设备的屏幕方向、语言区域、设备类型、屏幕密度、颜色模式等配置信息。 |
| ResourceManager_ErrorCode OH_ResourceManager_ReleaseConfiguration(ResourceManager_Configuration *configuration) | 释放OH_ResourceManager_GetConfiguration或OH_ResourceManager_GetResourceConfiguration函数申请的内存。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetString(const NativeResourceManager *mgr, uint32_t resId, char **resultValue, ...) | 获取指定资源ID对应的普通字符串或格式化字符串。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetStringByName(const NativeResourceManager *mgr, const char *resName, char **resultValue, ...) | 获取指定资源名称对应的普通字符串或格式化字符串。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetStringArray(const NativeResourceManager *mgr, uint32_t resId, char ***resultValue, uint32_t *resultLen) | 获取指定资源ID对应的字符串数组。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetStringArrayByName(const NativeResourceManager *mgr, const char *resName, char ***resultValue, uint32_t *resultLen) | 获取指定资源名称对应的字符串数组。 |
| ResourceManager_ErrorCode OH_ResourceManager_ReleaseStringArray(char ***resValue, uint32_t len) | 释放字符串数组内存。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetPluralString(const NativeResourceManager *mgr, uint32_t resId, uint32_t num, char **resultValue) | 获取指定资源ID对应的复数字符串。 中文环境下，字符串不区分单复数；其他语言环境下，字符串区分单复数，具体规则参考语言单复数规则。 在英语、德语等语言中，单复数类型包括基数词（如1、2、3）和序数词（如1st、2nd、3rd），本函数仅支持在基数词类型下使用。(API16废弃) |
| ResourceManager_ErrorCode OH_ResourceManager_GetPluralStringByName(const NativeResourceManager *mgr, const char *resName, uint32_t num, char **resultValue) | 获取指定资源名称对应的复数字符串。 中文环境下，字符串不区分单复数；其他语言环境下，字符串区分单复数，具体规则参考语言单复数规则。 在英语、德语等语言中，单复数类型包括基数词（如1、2、3）和序数词（如1st、2nd、3rd），本函数仅支持在基数词类型下使用。(API16废弃) |
| ResourceManager_ErrorCode OH_ResourceManager_GetIntPluralString(const NativeResourceManager *mgr, uint32_t resId, uint32_t num, char **resultValue, ...) | 通过指定资源ID、整数数量值和可变参数，获取对应的复数字符串并进行格式化。 中文环境下，字符串不区分单复数；其他语言环境下，字符串区分单复数，具体规则参考语言单复数规则。 在英语、德语等语言中，单复数类型包括基数词（如1、2、3）和序数词（如1st、2nd、3rd），本函数仅支持在基数词类型下使用。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetIntPluralStringByName(const NativeResourceManager *mgr, const char *resName, uint32_t num, char **resultValue, ...) | 通过指定资源名称、整数数量值和可变参数，获取对应的复数字符串并进行格式化。 中文环境下，字符串不区分单复数；其他语言环境下，字符串区分单复数，具体规则参考语言单复数规则。 在英语、德语等语言中，单复数类型包括基数词（如1、2、3）和序数词（如1st、2nd、3rd），本函数仅支持在基数词类型下使用。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetDoublePluralString(const NativeResourceManager *mgr, uint32_t resId, double num, char **resultValue, ...) | 通过指定资源ID、浮点数数量值和可变参数，获取对应的复数字符串并进行格式化。 中文环境下，字符串不区分单复数；其他语言环境下，字符串区分单复数，具体规则参考语言单复数规则。 在英语、德语等语言中，单复数类型包括基数词（如1、2、3）和序数词（如1st、2nd、3rd），本函数仅支持在基数词类型下使用。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetDoublePluralStringByName(const NativeResourceManager *mgr, const char *resName, double num, char **resultValue, ...) | 通过指定资源名称、浮点数数量值和可变参数，获取对应的复数字符串并进行格式化。 中文环境下，字符串不区分单复数；其他语言环境下，字符串区分单复数，具体规则参考语言单复数规则。 在英语、德语等语言中，单复数类型包括基数词（如1、2、3）和序数词（如1st、2nd、3rd），本函数仅支持在基数词类型下使用。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetColor(const NativeResourceManager *mgr, uint32_t resId, uint32_t *resultValue) | 获取指定资源ID对应的颜色资源值。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetColorByName(const NativeResourceManager *mgr, const char *resName, uint32_t *resultValue) | 获取指定资源名称对应的颜色资源值。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetInt(const NativeResourceManager *mgr, uint32_t resId, int *resultValue) | 获取指定资源ID对应的整数资源值。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetIntByName(const NativeResourceManager *mgr, const char *resName, int *resultValue) | 获取指定资源名称对应的整数资源值。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetFloat(const NativeResourceManager *mgr, uint32_t resId, float *resultValue) | 获取指定资源ID对应的浮点数资源值。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetFloatByName(const NativeResourceManager *mgr, const char *resName, float *resultValue) | 获取指定资源名称对应的浮点数资源值。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetBool(const NativeResourceManager *mgr, uint32_t resId, bool *resultValue) | 获取指定资源ID对应的布尔资源值。 |
| ResourceManager_ErrorCode OH_ResourceManager_GetBoolByName(const NativeResourceManager *mgr, const char *resName, bool *resultValue) | 获取指定资源名称对应的布尔资源值。 |
| ResourceManager_ErrorCode OH_ResourceManager_AddResource(const NativeResourceManager *mgr, const char *path) | 在应用程序运行时，动态加载overlay资源，实现主题切换或资源覆盖。 |
| ResourceManager_ErrorCode OH_ResourceManager_RemoveResource(const NativeResourceManager *mgr, const char *path) | 在应用程序运行时，移除指定的overlay资源，还原被覆盖前的资源。 |
 
 
  

## 函数说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### OH_ResourceManager_GetMediaBase64()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetMediaBase64(const NativeResourceManager *mgr, uint32_t resId, char **resultValue, uint64_t *resultLen, uint32_t density = 0)
```
 
**描述**
 
通过指定资源ID和屏幕密度，获取对应的media资源的Base64编码字符串。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| char **resultValue | 输出参数。返回Base64编码字符串指针，由malloc()分配内存，使用完后须通过free()释放。 |
| uint64_t *resultLen | 输出参数。返回Base64字符串长度，单位为Byte。 |
| density | 输入参数，可选。屏幕密度，取值范围请参考ScreenDensity。默认值为0，表示使用当前系统屏幕密度。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetMediaBase64Data()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetMediaBase64Data(const NativeResourceManager *mgr, uint32_t resId, char **resultValue, uint64_t *resultLen, uint32_t density)
```
 
**描述**
 
通过指定资源ID和屏幕密度，获取对应的media资源的Base64编码字符串。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| char **resultValue | 输出参数。返回Base64编码字符串指针，由malloc()分配内存，使用完后须通过free()释放。 |
| uint64_t *resultLen | 输出参数。返回Base64字符串长度，单位为Byte。 |
| uint32_t density | 输入参数。屏幕密度，取值范围请参考ScreenDensity。值为0表示使用当前系统屏幕密度。若不需要特定密度，请将此参数设置为0。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetMediaBase64ByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetMediaBase64ByName(const NativeResourceManager *mgr, const char *resName, char **resultValue, uint64_t *resultLen, uint32_t density = 0)
```
 
**描述**
 
通过指定资源名称和屏幕密度，获取对应的media资源的Base64编码字符串。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| char **resultValue | 输出参数。返回Base64编码字符串指针，由malloc()分配内存，使用完后须通过free()释放。 |
| uint64_t *resultLen | 输出参数。返回Base64字符串长度，单位为Byte。 |
| density | 输入参数，可选。屏幕密度，取值范围请参考ScreenDensity。默认值为0，表示使用当前系统屏幕密度。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetMediaBase64DataByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetMediaBase64DataByName(const NativeResourceManager *mgr, const char *resName, char **resultValue, uint64_t *resultLen, uint32_t density)
```
 
**描述**
 
通过指定资源名称和屏幕密度，获取对应的media资源的Base64编码字符串。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| char **resultValue | 输出参数。返回Base64编码字符串指针，由malloc()分配内存，使用完后须通过free()释放。 |
| uint64_t *resultLen | 输出参数。返回Base64字符串长度，单位为Byte。 |
| uint32_t density | 输入参数。屏幕密度，取值范围请参考ScreenDensity。值为0表示使用当前系统屏幕密度。若不需要特定密度，请将此参数设置为0。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetMedia()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetMedia(const NativeResourceManager *mgr, uint32_t resId, uint8_t **resultValue, uint64_t *resultLen, uint32_t density = 0)
```
 
**描述**
 
通过指定资源ID和屏幕密度，获取对应的media资源的二进制数据。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| uint8_t **resultValue | 输出参数。返回媒体数据指针，由malloc()分配内存，使用完后须通过free()释放。 |
| uint64_t *resultLen | 输出参数。返回数据长度，单位为Byte。 |
| density | 输入参数，可选。屏幕密度，取值范围请参考ScreenDensity。默认值为0，表示使用当前系统屏幕密度。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetMediaData()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetMediaData(const NativeResourceManager *mgr, uint32_t resId, uint8_t **resultValue, uint64_t *resultLen, uint32_t density)
```
 
**描述**
 
通过指定资源ID和屏幕密度，获取对应的media资源的二进制数据。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| uint8_t **resultValue | 输出参数。返回媒体数据指针，由malloc()分配内存，使用完后须通过free()释放。 |
| uint64_t *resultLen | 输出参数。返回数据长度，单位为Byte。 |
| uint32_t density | 输入参数。屏幕密度，取值范围请参考ScreenDensity。值为0表示使用当前系统屏幕密度。若不需要特定密度，请将此参数设置为0。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetMediaByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetMediaByName(const NativeResourceManager *mgr, const char *resName, uint8_t **resultValue, uint64_t *resultLen, uint32_t density = 0)
```
 
**描述**
 
通过指定资源名称和屏幕密度，获取对应的media资源的二进制数据。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| uint8_t **resultValue | 输出参数。返回媒体数据指针，由malloc()分配内存，使用完后须通过free()释放。 |
| uint64_t *resultLen | 输出参数。返回数据长度，单位为Byte。 |
| density | 输入参数，可选。屏幕密度，取值范围请参考ScreenDensity。默认值为0，表示使用当前系统屏幕密度。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetMediaDataByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetMediaDataByName(const NativeResourceManager *mgr, const char *resName, uint8_t **resultValue, uint64_t *resultLen, uint32_t density)
```
 
**描述**
 
通过指定资源名称和屏幕密度，获取对应的media资源的二进制数据。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| uint8_t **resultValue | 输出参数。返回媒体数据指针，由malloc()分配内存，使用完后须通过free()释放。 |
| uint64_t *resultLen | 输出参数。返回数据长度，单位为Byte。 |
| uint32_t density | 输入参数。屏幕密度，取值范围请参考ScreenDensity。值为0表示使用当前系统屏幕密度。若不需要特定密度，请将此参数设置为0。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetDrawableDescriptor()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetDrawableDescriptor(const NativeResourceManager *mgr, uint32_t resId, ArkUI_DrawableDescriptor **drawableDescriptor, uint32_t density = 0, uint32_t type = 0)
```
 
**描述**
 
通过指定资源ID、屏幕密度、图标类型，获取图标资源对应的DrawableDescriptor对象。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| ArkUI_DrawableDescriptor **drawableDescriptor | 输出参数。返回指向DrawableDescriptor对象的指针。 |
| density | 输入参数，可选。屏幕密度，取值范围请参考ScreenDensity。默认值为0，表示使用当前系统屏幕密度。 |
| type | 输入参数，可选。图标类型，默认值为0。 0：表示应用自身图标。 1：表示应用主题图标。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 |
 
 
  

### OH_ResourceManager_GetDrawableDescriptorData()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetDrawableDescriptorData(const NativeResourceManager *mgr, uint32_t resId, ArkUI_DrawableDescriptor **drawableDescriptor, uint32_t density, uint32_t type)
```
 
**描述**
 
通过指定资源ID、屏幕密度、图标类型，获取图标资源对应的DrawableDescriptor对象。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| ArkUI_DrawableDescriptor **drawableDescriptor | 输出参数。返回指向DrawableDescriptor对象的指针。 |
| uint32_t density | 输入参数。屏幕密度，取值范围请参考ScreenDensity。值为0表示使用当前系统屏幕密度。若不需要特定密度，请将此参数设置为0。 |
| uint32_t type | 输入参数。图标类型，若不需要特定图标类型，请将该参数设置为0。 0：表示应用自身图标。 1：表示应用主题图标。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 |
 
 
  

### OH_ResourceManager_GetDrawableDescriptorByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetDrawableDescriptorByName(const NativeResourceManager *mgr, const char *resName, ArkUI_DrawableDescriptor **drawableDescriptor, uint32_t density = 0, uint32_t type = 0)
```
 
**描述**
 
通过指定资源名称、屏幕密度、图标类型，获取图标资源对应的DrawableDescriptor对象。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| ArkUI_DrawableDescriptor **drawableDescriptor | 输出参数。返回指向DrawableDescriptor对象的指针。 |
| density | 输入参数，可选。屏幕密度，取值范围请参考ScreenDensity。默认值为0，表示使用当前系统屏幕密度。 |
| type | 输入参数，可选。图标类型，默认值为0。 0：表示应用自身图标。 1：表示应用主题图标。 2：表示应用动态图标。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 |
 
 
  

### OH_ResourceManager_GetDrawableDescriptorDataByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetDrawableDescriptorDataByName(const NativeResourceManager *mgr, const char *resName, ArkUI_DrawableDescriptor **drawableDescriptor, uint32_t density, uint32_t type)
```
 
**描述**
 
通过指定资源名称和屏幕密度，获取对应的图标资源的DrawableDescriptor对象。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| ArkUI_DrawableDescriptor **drawableDescriptor | 输出参数。返回指向DrawableDescriptor对象的指针。 |
| uint32_t density | 输入参数，屏幕密度，取值范围请参考ScreenDensity。值为0表示使用当前系统屏幕密度。若不需要特定密度，请将此参数设置为0。 |
| uint32_t type | 输入参数。图标类型，若不需要特定图标类型，请将该参数设置为0。 0：表示应用自身图标。 1：表示主题图标。 2：表示动态图标。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 |
 
 
  

### OH_ResourceManager_GetSymbol()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetSymbol(const NativeResourceManager *mgr, uint32_t resId, uint32_t *resultValue)
```
 
**描述**
 
获取指定资源ID对应的Symbol图标的Unicode编码。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| uint32_t *resultValue | 输出参数。返回Symbol图标的Unicode编码。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 |
 
 
  

### OH_ResourceManager_GetSymbolByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetSymbolByName(const NativeResourceManager *mgr, const char *resName, uint32_t *resultValue)
```
 
**描述**
 
获取指定资源名称对应的Symbol图标的Unicode编码。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| uint32_t *resultValue | 输出参数。返回Symbol图标的Unicode编码。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 |
 
 
  

### OH_ResourceManager_GetLocales()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetLocales(const NativeResourceManager *mgr, char ***resultValue, uint32_t *resultLen, bool includeSystem = false)
```
 
**描述**
 
获取应用支持的语言列表。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| char ***resultValue | 输出参数。返回指向语言列表数组的指针，由此函数分配内存，使用完后须通过OH_ResourceManager_ReleaseStringArray释放。 |
| uint32_t *resultLen | 输出参数。返回语言列表长度。 |
| includeSystem | 输入参数，可选。表示是否包含系统资源，true表示包含系统资源，false表示不包含系统资源。默认值为false。 当使用系统资源管理对象获取语言列表时，始终返回系统资源语言列表。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetLocalesData()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetLocalesData(const NativeResourceManager *mgr, char ***resultValue, uint32_t *resultLen, bool includeSystem)
```
 
**描述**
 
获取应用支持的语言列表。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| char ***resultValue | 输出参数。返回指向语言列表数组的指针，由此函数分配内存，使用完后须通过OH_ResourceManager_ReleaseStringArray释放。 |
| uint32_t *resultLen | 输出参数。返回语言列表长度。 |
| bool includeSystem | 输入参数。表示是否包含系统资源，true表示包含系统资源，false表示不包含系统资源。 当使用系统资源管理对象获取语言列表时，始终返回系统资源语言列表。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetConfiguration()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetConfiguration(const NativeResourceManager *mgr, ResourceManager_Configuration *configuration)
```
 
**描述**
 
获取设备的屏幕方向、语言区域、设备类型、屏幕密度、颜色模式等配置信息。
 
**起始版本：** 12
 
**废弃版本：** 20
 
**替代接口：** [OH_ResourceManager_GetResourceConfiguration](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohresmgr-h#oh_resourcemanager_getresourceconfiguration)
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| ResourceManager_Configuration *configuration | 输出参数。返回设备配置信息，其中screenDensity为设备屏幕密度（dpi）除以160取整后的值。 configuration中的locale字符串由此函数分配内存，使用完后需通过OH_ResourceManager_ReleaseConfiguration释放locale。若configuration指针由malloc()分配内存，使用完后须通过free()释放。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_SYSTEM_RES_MANAGER_GET_FAILED，表示访问系统资源失败。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetResourceConfiguration()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetResourceConfiguration(const NativeResourceManager *mgr, ResourceManager_Configuration *configuration)
```
 
**描述**
 
获取设备的屏幕方向、语言区域、设备类型、屏幕密度、颜色模式等配置信息。
 
**起始版本：** 20
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| ResourceManager_Configuration *configuration | 输出参数。返回设备配置信息，其中screenDensity的值为设备屏幕密度（dpi）。 configuration中的locale字符串由此函数分配内存，使用完后需通过OH_ResourceManager_ReleaseConfiguration释放locale。若configuration指针由malloc()分配内存，使用完后须通过free()释放。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_SYSTEM_RES_MANAGER_GET_FAILED，表示访问系统资源失败。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_ReleaseConfiguration()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_ReleaseConfiguration(ResourceManager_Configuration *configuration)
```
 
**描述**
 
释放[OH_ResourceManager_GetConfiguration](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohresmgr-h#oh_resourcemanager_getconfiguration)或[OH_ResourceManager_GetResourceConfiguration](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohresmgr-h#oh_resourcemanager_getresourceconfiguration)函数申请的内存。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| ResourceManager_Configuration *configuration | 输入参数。指向需要释放内存的ResourceManager_Configuration对象的指针。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 |
 
 
  

### OH_ResourceManager_GetString()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetString(const NativeResourceManager *mgr, uint32_t resId, char **resultValue, ...)
```
 
**描述**
 
获取指定资源ID对应的普通字符串或格式化字符串。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| char **resultValue | 输出参数。返回字符串指针，由malloc()分配内存，使用完后须通过free()释放。 |
| ... | 输入参数，可选。表示可变参数列表，用于格式化字符串，支持const char*、int、float三种类型。 获取普通字符串时，无需填写；获取格式化字符串时，必填，须按字符串中的占位符顺序依次传入对应类型的可变参数，参数数量、类型与字符串的占位符保持一致，如字符串包含%d、%s、%f三个占位符，调用方式为OH_ResourceManager_GetString(mgr, resId, resultValue, 10, "format", 10.10)。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetStringByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetStringByName(const NativeResourceManager *mgr, const char *resName, char **resultValue, ...)
```
 
**描述**
 
获取指定资源名称对应的普通字符串或格式化字符串。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| char **resultValue | 输出参数。返回字符串指针，由malloc()分配内存，使用完后须通过free()释放。 |
| ... | 输入参数，可选。表示可变参数列表，用于格式化字符串，支持const char*、int、float三种类型。 获取普通字符串时，无需填写；获取格式化字符串时，必填，须按字符串中的占位符顺序依次传入对应类型的可变参数，参数数量、类型与字符串的占位符保持一致，如字符串包含%d、%s、%f三个占位符，调用方式为OH_ResourceManager_GetStringByName(mgr, resName, resultValue, 10, "format", 10.10)。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetStringArray()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetStringArray(const NativeResourceManager *mgr, uint32_t resId, char ***resultValue, uint32_t *resultLen)
```
 
**描述**
 
获取指定资源ID对应的字符串数组。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| char ***resultValue | 输出参数。返回字符串数组指针。由此函数分配内存，使用完后须通过OH_ResourceManager_ReleaseStringArray释放。 |
| uint32_t *resultLen | 输出参数。返回字符串数组长度。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetStringArrayByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetStringArrayByName(const NativeResourceManager *mgr, const char *resName, char ***resultValue, uint32_t *resultLen)
```
 
**描述**
 
获取指定资源名称对应的字符串数组。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| char ***resultValue | 输出参数。返回字符串数组指针。由此函数分配内存，使用完后须通过OH_ResourceManager_ReleaseStringArray释放。 |
| uint32_t *resultLen | 输出参数。返回字符串数组长度。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_ReleaseStringArray()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_ReleaseStringArray(char ***resValue, uint32_t len)
```
 
**描述**
 
释放字符串数组内存。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| char ***resValue | 输入参数。待释放的字符串数组指针。 |
| uint32_t len | 输入参数。字符串数组长度。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 |
 
 
  

### OH_ResourceManager_GetPluralString()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetPluralString(const NativeResourceManager *mgr, uint32_t resId, uint32_t num, char **resultValue)
```
 
**描述**
 
获取指定资源ID对应的复数字符串。
 
 中文环境下，字符串不区分单复数；其他语言环境下，字符串区分单复数，具体规则参考[语言单复数规则](https://www.unicode.org/cldr/charts/45/supplemental/language_plural_rules.html)。
 
 在英语、德语等语言中，单复数类型包括基数词（如1、2、3）和序数词（如1st、2nd、3rd），本函数仅支持在基数词类型下使用。
 
**起始版本：** 12
 
**废弃版本：** 16
 
**替代接口：** [OH_ResourceManager_GetIntPluralString](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohresmgr-h#oh_resourcemanager_getintpluralstring)
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| uint32_t num | 输入参数。数量值，用于根据当前语言的复数规则获取对应的复数字符串。 |
| char **resultValue | 输出参数。返回字符串指针。由malloc()分配内存，使用完后须通过free()释放。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetPluralStringByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetPluralStringByName(const NativeResourceManager *mgr, const char *resName, uint32_t num, char **resultValue)
```
 
**描述**
 
获取指定资源名称对应的复数字符串。
 
 中文环境下，字符串不区分单复数；其他语言环境下，字符串区分单复数，具体规则参考[语言单复数规则](https://www.unicode.org/cldr/charts/45/supplemental/language_plural_rules.html)。
 
 在英语、德语等语言中，单复数类型包括基数词（如1、2、3）和序数词（如1st、2nd、3rd），本函数仅支持在基数词类型下使用。
 
**起始版本：** 12
 
**废弃版本：** 16
 
**替代接口：** [OH_ResourceManager_GetIntPluralStringByName](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohresmgr-h#oh_resourcemanager_getintpluralstringbyname)
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| uint32_t num | 输入参数。数量值，用于根据当前语言的复数规则获取对应的复数字符串。 |
| char **resultValue | 输出参数。返回字符串指针。由malloc()分配内存，使用完后须通过free()释放。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetIntPluralString()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetIntPluralString(const NativeResourceManager *mgr, uint32_t resId, uint32_t num, char **resultValue, ...)
```
 
**描述**
 
通过指定资源ID、整数数量值和可变参数，获取对应的复数字符串并进行格式化。
 
 中文环境下，字符串不区分单复数；其他语言环境下，字符串区分单复数，具体规则参考[语言单复数规则](https://www.unicode.org/cldr/charts/45/supplemental/language_plural_rules.html)。
 
 在英语、德语等语言中，单复数类型包括基数词（如1、2、3）和序数词（如1st、2nd、3rd），本函数仅支持在基数词类型下使用。
 
**起始版本：** 18
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| uint32_t num | 输入参数。数量值（整数），用于根据当前语言的复数规则获取对应的复数字符串。 |
| char **resultValue | 输出参数。返回字符串指针。由malloc()分配内存，使用完后须通过free()释放。 |
| ... | 输入参数，可选。表示可变参数列表，用于格式化字符串，支持const char*、int、float三种类型。 获取格式化字符串时，须按字符串中的占位符顺序依次传入对应类型的可变参数，参数数量、类型与字符串的占位符保持一致，如字符串包含%d、%s、%f三个占位符，调用方式为OH_ResourceManager_GetIntPluralString(mgr, resId, 10, resultValue, 10, "format", 10.10)。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetIntPluralStringByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetIntPluralStringByName(const NativeResourceManager *mgr, const char *resName, uint32_t num, char **resultValue, ...)
```
 
**描述**
 
通过指定资源名称、整数数量值和可变参数，获取对应的复数字符串并进行格式化。
 
 中文环境下，字符串不区分单复数；其他语言环境下，字符串区分单复数，具体规则参考[语言单复数规则](https://www.unicode.org/cldr/charts/45/supplemental/language_plural_rules.html)。
 
 在英语、德语等语言中，单复数类型包括基数词（如1、2、3）和序数词（如1st、2nd、3rd），本函数仅支持在基数词类型下使用。
 
**起始版本：** 18
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| uint32_t num | 输入参数。数量值（整数），用于根据当前语言的复数规则获取对应的复数字符串。 |
| char **resultValue | 输出参数。返回字符串指针。由malloc()分配内存，使用完后须通过free()释放。 |
| ... | 输入参数，可选。表示可变参数列表，用于格式化字符串，支持const char*、int、float三种类型。 获取格式化字符串时，须按字符串中的占位符顺序依次传入对应类型的可变参数，参数数量、类型与字符串的占位符保持一致，如字符串包含%d、%s、%f三个占位符，调用方式为OH_ResourceManager_GetIntPluralStringByName(mgr, resName, 10, resultValue, 10, "format", 10.10)。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetDoublePluralString()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetDoublePluralString(const NativeResourceManager *mgr, uint32_t resId, double num, char **resultValue, ...)
```
 
**描述**
 
通过指定资源ID、浮点数数量值和可变参数，获取对应的复数字符串并进行格式化。
 
 中文环境下，字符串不区分单复数；其他语言环境下，字符串区分单复数，具体规则参考[语言单复数规则](https://www.unicode.org/cldr/charts/45/supplemental/language_plural_rules.html)。
 
 在英语、德语等语言中，单复数类型包括基数词（如1、2、3）和序数词（如1st、2nd、3rd），本函数仅支持在基数词类型下使用。
 
**起始版本：** 18
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| double num | 输入参数。数量值（浮点数），用于根据当前语言的复数规则获取对应的复数字符串。 |
| char **resultValue | 输出参数。返回字符串指针。由malloc()分配内存，使用完后须通过free()释放。 |
| ... | 输入参数，可选。表示可变参数列表，用于格式化字符串，支持const char*、int、float三种类型。 获取格式化字符串时，须按字符串中的占位符顺序依次传入对应类型的可变参数，参数数量、类型与字符串的占位符保持一致，如字符串包含%d、%s、%f三个占位符，调用方式为OH_ResourceManager_GetDoublePluralString(mgr, resId, 1.1, resultValue, 10, "format", 10.10)。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetDoublePluralStringByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetDoublePluralStringByName(const NativeResourceManager *mgr, const char *resName, double num, char **resultValue, ...)
```
 
**描述**
 
通过指定资源名称、浮点数数量值和可变参数，获取对应的复数字符串并进行格式化。
 
 中文环境下，字符串不区分单复数；其他语言环境下，字符串区分单复数，具体规则参考[语言单复数规则](https://www.unicode.org/cldr/charts/45/supplemental/language_plural_rules.html)。
 
 在英语、德语等语言中，单复数类型包括基数词（如1、2、3）和序数词（如1st、2nd、3rd），本函数仅支持在基数词类型下使用。
 
**起始版本：** 18
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| double num | 输入参数。数量值（浮点数），用于根据当前语言的复数规则获取对应的复数字符串。 |
| char **resultValue | 输出参数。返回字符串指针。由malloc()分配内存，使用完后须通过free()释放。 |
| ... | 输入参数，可选。表示可变参数列表，用于格式化字符串，支持const char*、int、float三种类型。 获取格式化字符串时，须按字符串中的占位符顺序依次传入对应类型的可变参数，参数数量、类型与字符串的占位符保持一致，如字符串包含%d、%s、%f三个占位符，调用方式为OH_ResourceManager_GetDoublePluralStringByName(mgr, resName, 1.1, resultValue, 10, "format", 10.10)。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 返回ERROR_CODE_OUT_OF_MEMORY，表示内存溢出。 |
 
 
  

### OH_ResourceManager_GetColor()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetColor(const NativeResourceManager *mgr, uint32_t resId, uint32_t *resultValue)
```
 
**描述**
 
获取指定资源ID对应的颜色资源值。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| uint32_t *resultValue | 输出参数。返回颜色资源值。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 |
 
 
  

### OH_ResourceManager_GetColorByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetColorByName(const NativeResourceManager *mgr, const char *resName, uint32_t *resultValue)
```
 
**描述**
 
获取指定资源名称对应的颜色资源值。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| uint32_t *resultValue | 输出参数。返回颜色资源值。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 |
 
 
  

### OH_ResourceManager_GetInt()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetInt(const NativeResourceManager *mgr, uint32_t resId, int *resultValue)
```
 
**描述**
 
获取指定资源ID对应的整数资源值。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| int *resultValue | 输出参数。返回整数资源值。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 |
 
 
  

### OH_ResourceManager_GetIntByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetIntByName(const NativeResourceManager *mgr, const char *resName, int *resultValue)
```
 
**描述**
 
获取指定资源名称对应的整数资源值。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| int *resultValue | 输出参数。返回整数资源值。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 |
 
 
  

### OH_ResourceManager_GetFloat()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetFloat(const NativeResourceManager *mgr, uint32_t resId, float *resultValue)
```
 
**描述**
 
获取指定资源ID对应的浮点数资源值。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| float *resultValue | 输出参数。返回浮点数资源值。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 |
 
 
  

### OH_ResourceManager_GetFloatByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetFloatByName(const NativeResourceManager *mgr, const char *resName, float *resultValue)
```
 
**描述**
 
获取指定资源名称对应的浮点数资源值。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| float *resultValue | 输出参数。返回浮点数资源值。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 |
 
 
  

### OH_ResourceManager_GetBool()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetBool(const NativeResourceManager *mgr, uint32_t resId, bool *resultValue)
```
 
**描述**
 
获取指定资源ID对应的布尔资源值。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| uint32_t resId | 输入参数。资源ID。 |
| bool *resultValue | 输出参数。返回布尔资源值。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_ID_NOT_FOUND，表示无效的资源ID。 返回ERROR_CODE_RES_NOT_FOUND_BY_ID，表示根据资源ID未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 |
 
 
  

### OH_ResourceManager_GetBoolByName()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_GetBoolByName(const NativeResourceManager *mgr, const char *resName, bool *resultValue)
```
 
**描述**
 
获取指定资源名称对应的布尔资源值。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *resName | 输入参数。资源名称。 |
| bool *resultValue | 输出参数。返回布尔资源值。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_RES_NAME_NOT_FOUND，表示无效的资源名称。 返回ERROR_CODE_RES_NOT_FOUND_BY_NAME，表示根据资源名称未找到匹配的资源。 返回ERROR_CODE_RES_REF_TOO_MUCH，表示资源存在循环引用。 |
 
 
  

### OH_ResourceManager_AddResource()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_AddResource(const NativeResourceManager *mgr, const char *path)
```
 
**描述**
 
在应用程序运行时，动态加载overlay资源，实现主题切换或资源覆盖。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *path | 输入参数。待加载的HSP或HAP资源包的绝对路径。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_OVERLAY_RES_PATH_INVALID，表示无效的overlay路径。 |
 
 
  

### OH_ResourceManager_RemoveResource()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
ResourceManager_ErrorCode OH_ResourceManager_RemoveResource(const NativeResourceManager *mgr, const char *path)
```
 
**描述**
 
在应用程序运行时，移除指定的overlay资源，还原被覆盖前的资源。
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const NativeResourceManager *mgr | 输入参数。指向NativeResourceManager对象的指针，此指针通过OH_ResourceManager_InitNativeResourceManager函数获取。 |
| const char *path | 输入参数。待移除的HSP或HAP资源包的绝对路径。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| ResourceManager_ErrorCode | 返回错误码。 返回SUCCESS，表示成功。 返回ERROR_CODE_INVALID_INPUT_PARAMETER，表示输入参数无效。可能的原因：1.参数类型不正确；2.参数验证失败。 返回ERROR_CODE_OVERLAY_RES_PATH_INVALID，表示无效的overlay路径。 |
