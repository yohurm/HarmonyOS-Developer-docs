# OH_Drawing_RunBuffer

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-drawing-oh-drawing-runbuffer
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct {...} OH_Drawing_RunBuffer
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

结构体用于描述一块内存，描述文字和位置信息。
 
**起始版本：** 11
 
**相关模块：** [Drawing](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-drawing)
 
**所在头文件：** [drawing_text_blob.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-drawing-text-blob-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| uint16_t* glyphs | 存储字形索引。 |
| float* pos | 存储文字的位置。单位为物理像素px。 |
| char* utf8text | 存储文字UTF-8编码。 |
| uint32_t* clusters | 存储文字簇UTF-8编码（簇指的是集合）。 |
