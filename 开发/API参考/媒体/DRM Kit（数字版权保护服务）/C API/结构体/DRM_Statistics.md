# DRM_Statistics

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-drm-drm-statistics
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct DRM_Statistics {...} DRM_Statistics
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

MediaKeySystem的统计信息。
 
**起始版本：** 11
 
**相关模块：** [Drm](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-drm)
 
**所在头文件：** [native_drm_common.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-drm-common-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| uint32_t statisticsCount | 度量信息的数量，表示statisticsName和statisticsDescription数组中有效元素的个数。取值范围为[0, MAX_STATISTICS_COUNT]。 |
| char statisticsName[MAX_STATISTICS_COUNT][MAX_STATISTICS_NAME_LEN] | 度量信息名称数组，每行存储一个度量项的名称，如"DecryptionOperations"（解密操作次数）、"KeySessions"（密钥会话数）等。数组维度由MAX_STATISTICS_COUNT和MAX_STATISTICS_NAME_LEN宏定义。 |
| char statisticsDescription[MAX_STATISTICS_COUNT][MAX_STATISTICS_BUFFER_LEN] | 度量信息描述数组，每行存储对应statisticsName的度量值。描述内容通常包含数值、百分比或其他格式的统计数据。数组维度由MAX_STATISTICS_COUNT和MAX_STATISTICS_BUFFER_LEN宏定义。 |
