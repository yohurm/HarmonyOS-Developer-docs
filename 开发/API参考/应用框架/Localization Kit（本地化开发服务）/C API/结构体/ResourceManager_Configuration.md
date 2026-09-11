# ResourceManager_Configuration

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-resourcemanager-resourcemanager-configuration
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct ResourceManager_Configuration {...} ResourceManager_Configuration
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

设备状态的结构体。
 
**起始版本：** 12
 
**相关模块：** [resourcemanager](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-resourcemanager)
 
**所在头文件：** [resmgr_common.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-resmgr-common-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| ResourceManager_Direction direction | 表示屏幕方向。 |
| char* locale | 表示语言、文字、国家或地区，如zh_Hans_CN。 |
| ResourceManager_DeviceType deviceType | 表示设备类型。 |
| ScreenDensity screenDensity | 表示屏幕密度。 |
| ResourceManager_ColorMode colorMode | 表示颜色模式。 |
| uint32_t mcc | 表示移动国家码。 |
| uint32_t mnc | 表示移动网络码。 |
| uint32_t reserved[20] | 保留属性。 |
