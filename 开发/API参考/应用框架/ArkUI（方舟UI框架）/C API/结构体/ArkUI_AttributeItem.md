# ArkUI_AttributeItem

更新时间：2026-09-24 09:52:23

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-arkui-nativemodule-arkui-attributeitem
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct {...} ArkUI_AttributeItem
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

定义[setAttribute](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-arkui-nativemodule-arkui-nativenodeapi-1#setattribute)函数的通用入参结构。各个属性设置接口可选择使用其中的成员变量来存储特定类型的参数数据。
 
**起始版本：** 12
 
**相关模块：** [ArkUI_NativeModule](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-arkui-nativemodule)
 
**所在头文件：** [common_type.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-common-type-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| const ArkUI_NumberValue* value | 数字数组，用于存储数字类型的属性参数，数组长度由size指定。 |
| int32_t size | value数组的长度，需配合变量value使用。 |
| const char* string | 字符串，用于存储字符串类型的属性参数。 |
| void* object | 对象数据，用于存储对象类型的属性参数。 |
