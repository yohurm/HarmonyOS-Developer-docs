# Asset_Result

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-assettype-asset-result
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct {...} Asset_Result
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

单条关键资产的查询结果。
 
**起始版本：** 11
 
**相关模块：** [AssetType](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-assettype)
 
**所在头文件：** [asset_type.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-asset-type-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| uint32_t count | 关键资产属性的个数。 |
| Asset_Attr *attrs | 指向关键资产属性数组的指针。 |
