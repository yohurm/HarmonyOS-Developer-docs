# OH_ImageProcessing

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-imageprocessing-oh-imageprocessing
**支持设备：** Phone | PC/2in1 | Tablet | TV

```text
typedef struct OH_ImageProcessing OH_ImageProcessing
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV

提供OH_ImageProcessing结构体声明。
 
定义一个初始化为空的OH_ImageProcessing指针，并调用[OH_ImageProcessing_Create](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-image-processing-h#oh_imageprocessing_create)来创建图片处理实例。调用该接口前，应确保传入的指针为空。用户可根据不同的图片处理类型，分别创建多个图片处理实例。
 
**起始版本：** 13
 
**相关模块：** [ImageProcessing](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-imageprocessing)
 
**所在头文件：** [image_processing_types.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-image-processing-types-h)
