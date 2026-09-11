# Print_PrintAttributes

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-oh-print-print-printattributes
**支持设备：** Phone | PC/2in1 | Tablet

```text
typedef struct {...} Print_PrintAttributes
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet

表示打印属性结构体，用于配置打印任务的各项属性（如打印范围、纸张尺寸、边距、份数、双面模式、色彩模式、打印方向及打印选项等），适用于需要对打印输出进行精细化控制的场景。
 
**起始版本：** 13
 
**相关模块：** [OH_Print](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-oh-print)
 
**所在头文件：** [ohprint.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohprint-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet
 

| 名称 | 描述 |
| --- | --- |
| Print_Range pageRange | 打印范围。 |
| Print_PageSize pageSize | 打印纸张尺寸。 |
| Print_Margin pageMargin | 打印边距。 |
| uint32_t copyNumber | 份数。取值范围：大于等于1。 |
| uint32_t duplexMode | 双面模式。有效取值参见Print_DuplexMode枚举定义。 |
| uint32_t colorMode | 色彩模式。有效取值参见Print_ColorMode枚举定义。 |
| bool isSequential | 顺序打印。 true 表示顺序打印，false 表示逆序打印。 |
| bool isLandscape | 打印方向（是否横向）。 true 表示打印方向为横向，false 表示打印方向为纵向。 |
| bool hasOption | 打印选项标志。 true 表示有打印选项（options 字段有效），false 表示没有打印选项（options 字段无效）。 |
| char options[256] | 打印选项，用于传递额外的打印配置参数。仅在 hasOption 为 true 时生效，最大长度255个字符。 |
