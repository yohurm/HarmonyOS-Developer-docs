# drawing_pixel_map.h

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-drawing-pixel-map-h
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

声明与绘图模块中的像素图对象相关的函数。支持从图像框架定义的像素图对象中获取本模块定义的像素图对象，支持解除两者之间的关系。
 
本模块为单线程模型策略，需要调用方自行管理线程安全和上下文状态的切换。
 
**引用文件：** <native_drawing/drawing_pixel_map.h>
 
**库：** libnative_drawing.so
 
**系统能力：** SystemCapability.Graphic.Graphic2D.NativeDrawing
 
**起始版本：** 12
 
**相关模块：** [Drawing](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-drawing)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 结构体


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | typedef关键字 | 描述 |
| --- | --- | --- |
| NativePixelMap_ | NativePixelMap_ | 声明由图像框架定义的像素图对象。 |
| OH_PixelmapNative | OH_PixelmapNative | 声明由图像框架定义的像素图对象。 |
 
 
  

### 函数


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| OH_Drawing_PixelMap* OH_Drawing_PixelMapGetFromNativePixelMap(NativePixelMap_* nativePixelMap) | 从图像框架定义的像素图对象中获取本模块定义的像素图对象。对象使用完毕后，调用OH_Drawing_PixelMapDissolve解除关系，否则会引发内存泄漏问题。 |
| OH_Drawing_PixelMap* OH_Drawing_PixelMapGetFromOhPixelMapNative(OH_PixelmapNative* pixelmapNative) | 从图像框架定义的像素图对象中获取本模块定义的像素图对象。对象使用完毕后，调用OH_Drawing_PixelMapDissolve解除关系，否则会引发内存泄漏问题。 |
| void OH_Drawing_PixelMapDissolve(OH_Drawing_PixelMap* pixelMap) | 解除本模块定义的像素图对象和图像框架定义的像素图对象之间的关系。必须先调用OH_Drawing_PixelMapGetFromNativePixelMap或OH_Drawing_PixelMapGetFromOhPixelMapNative获取像素图对象并建立关联关系后，才能调用本方法解除该关系。 |
 
 
  

## 函数说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### OH_Drawing_PixelMapGetFromNativePixelMap()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
OH_Drawing_PixelMap* OH_Drawing_PixelMapGetFromNativePixelMap(NativePixelMap_* nativePixelMap)
```
 
**描述**
 
从图像框架定义的像素图对象中获取本模块定义的像素图对象。对象使用完毕后，调用[OH_Drawing_PixelMapDissolve](#oh_drawing_pixelmapdissolve)解除关系，否则会引发内存泄漏问题。
 
**系统能力：** SystemCapability.Graphic.Graphic2D.NativeDrawing
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| NativePixelMap_* nativePixelMap | 指向图像框架定义的像素图对象NativePixelMap_的指针。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| OH_Drawing_PixelMap* | 返回一个指向本模块定义的像素图对象OH_Drawing_PixelMap的指针。如果返回NULL，表示获取失败；原因是参数nativePixelMap为NULL。 |
 
 
  

### OH_Drawing_PixelMapGetFromOhPixelMapNative()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
OH_Drawing_PixelMap* OH_Drawing_PixelMapGetFromOhPixelMapNative(OH_PixelmapNative* pixelmapNative)
```
 
**描述**
 
从图像框架定义的像素图对象中获取本模块定义的像素图对象。对象使用完毕后，调用[OH_Drawing_PixelMapDissolve](#oh_drawing_pixelmapdissolve)解除关系，否则会引发内存泄漏问题。
 
**系统能力：** SystemCapability.Graphic.Graphic2D.NativeDrawing
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| OH_PixelmapNative* pixelmapNative | 指向图像框架定义的像素图对象OH_PixelmapNative的指针。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| OH_Drawing_PixelMap* | 返回一个指向本模块定义的像素图对象OH_Drawing_PixelMap的指针。如果返回NULL，表示获取失败；原因是参数pixelmapNative为NULL。 |
 
 
  

### OH_Drawing_PixelMapDissolve()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
void OH_Drawing_PixelMapDissolve(OH_Drawing_PixelMap* pixelMap)
```
 
**描述**
 
解除本模块定义的像素图对象和图像框架定义的像素图对象之间的关系。必须先调用[OH_Drawing_PixelMapGetFromNativePixelMap](#oh_drawing_pixelmapgetfromnativepixelmap)或[OH_Drawing_PixelMapGetFromOhPixelMapNative](#oh_drawing_pixelmapgetfromohpixelmapnative)获取像素图对象并建立关联关系后，才能调用本方法解除该关系。
 
**系统能力：** SystemCapability.Graphic.Graphic2D.NativeDrawing
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| OH_Drawing_PixelMap* pixelMap | 指向像素图对象OH_Drawing_PixelMap的指针。 |
