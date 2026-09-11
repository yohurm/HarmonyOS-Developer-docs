# drawing_point.h

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-drawing-point-h
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

文件中定义了与坐标点相关的功能函数，支持创建、获取、设置、取反、偏移及销毁坐标点对象等操作，便于在2D图形绘制中对坐标点进行管理与变换。
 
本模块为单线程模型策略，需要调用方自行管理线程安全和上下文状态的切换。
 
**引用文件：** <native_drawing/drawing_point.h>
 
**库：** libnative_drawing.so
 
**系统能力：** SystemCapability.Graphic.Graphic2D.NativeDrawing
 
**起始版本：** 11
 
**相关模块：** [Drawing](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-drawing)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 函数


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| OH_Drawing_Point* OH_Drawing_PointCreate(float x, float y) | 创建一个坐标点对象。当此坐标点对象不再需要时，必须调用OH_Drawing_PointDestroy销毁并回收内存。 |
| OH_Drawing_ErrorCode OH_Drawing_PointGetX(const OH_Drawing_Point* point, float* x) | 获取坐标点的x轴坐标值。 |
| OH_Drawing_ErrorCode OH_Drawing_PointGetY(const OH_Drawing_Point* point, float* y) | 获取坐标点的y轴坐标值。 |
| OH_Drawing_ErrorCode OH_Drawing_PointSet(OH_Drawing_Point* point, float x, float y) | 设置坐标点的x轴和y轴坐标。 |
| OH_Drawing_ErrorCode OH_Drawing_PointNegate(OH_Drawing_Point* point) | 对坐标点的x轴和y轴坐标取反。 |
| OH_Drawing_ErrorCode OH_Drawing_PointOffset(OH_Drawing_Point* point, float dx, float dy) | 将坐标点沿x轴和y轴方向偏移指定距离。 |
| void OH_Drawing_PointDestroy(OH_Drawing_Point* point) | 销毁坐标点对象并回收该对象占用的内存。需在OH_Drawing_PointCreate创建对象后且该对象不再使用时调用。 |
 
 
  

## 函数说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### OH_Drawing_PointCreate()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
OH_Drawing_Point* OH_Drawing_PointCreate(float x, float y)
```
 
**描述**
 
创建一个坐标点对象。当此坐标点对象不再需要时，必须调用[OH_Drawing_PointDestroy](#oh_drawing_pointdestroy)销毁并回收内存。
 
**系统能力：** SystemCapability.Graphic.Graphic2D.NativeDrawing
 
**起始版本：** 11
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| float x | 表示坐标点的x轴坐标，单位为物理像素px。 |
| float y | 表示坐标点的y轴坐标，单位为物理像素px。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| OH_Drawing_Point* | 函数返回指向创建的坐标点对象的指针。 |
 
 
  

### OH_Drawing_PointGetX()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
OH_Drawing_ErrorCode OH_Drawing_PointGetX(const OH_Drawing_Point* point, float* x)
```
 
**描述**
 
获取坐标点的x轴坐标值。
 
**系统能力：** SystemCapability.Graphic.Graphic2D.NativeDrawing
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const OH_Drawing_Point* point | 指向坐标点对象OH_Drawing_Point的指针。 |
| float* x | 输出参数，用于接收坐标点的x轴坐标值，单位为物理像素px。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| OH_Drawing_ErrorCode | 函数返回执行错误码。 返回OH_DRAWING_SUCCESS，表示执行成功。 返回OH_DRAWING_ERROR_INVALID_PARAMETER，表示参数point或者x为空。 |
 
 
  

### OH_Drawing_PointGetY()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
OH_Drawing_ErrorCode OH_Drawing_PointGetY(const OH_Drawing_Point* point, float* y)
```
 
**描述**
 
获取坐标点的y轴坐标值。
 
**系统能力：** SystemCapability.Graphic.Graphic2D.NativeDrawing
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| const OH_Drawing_Point* point | 指向坐标点对象OH_Drawing_Point的指针。 |
| float* y | 输出参数，用于接收坐标点的y轴坐标值，单位为物理像素px。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| OH_Drawing_ErrorCode | 函数返回执行错误码。 返回OH_DRAWING_SUCCESS，表示执行成功。 返回OH_DRAWING_ERROR_INVALID_PARAMETER，表示参数point或者y为空。 |
 
 
  

### OH_Drawing_PointSet()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
OH_Drawing_ErrorCode OH_Drawing_PointSet(OH_Drawing_Point* point, float x, float y)
```
 
**描述**
 
设置坐标点的x轴和y轴坐标。
 
**系统能力：** SystemCapability.Graphic.Graphic2D.NativeDrawing
 
**起始版本：** 12
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| OH_Drawing_Point* point | 指向坐标点对象OH_Drawing_Point的指针。 |
| float x | 表示坐标点的x轴坐标，单位为物理像素px。 |
| float y | 表示坐标点的y轴坐标，单位为物理像素px。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| OH_Drawing_ErrorCode | 函数返回执行错误码。 返回OH_DRAWING_SUCCESS，表示执行成功。 返回OH_DRAWING_ERROR_INVALID_PARAMETER，表示参数point为空。 |
 
 
  

### OH_Drawing_PointNegate()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
OH_Drawing_ErrorCode OH_Drawing_PointNegate(OH_Drawing_Point* point)
```
 
**描述**
 
对坐标点的x轴和y轴坐标取反。
 
**起始版本：** 26.0.0
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| OH_Drawing_Point* point | 指向坐标点对象OH_Drawing_Point的指针。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| OH_Drawing_ErrorCode | 函数返回执行错误码。 返回OH_DRAWING_SUCCESS，表示执行成功。 返回OH_DRAWING_ERROR_INCORRECT_PARAMETER，表示参数point为空。 |
 
 
  

### OH_Drawing_PointOffset()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
OH_Drawing_ErrorCode OH_Drawing_PointOffset(OH_Drawing_Point* point, float dx, float dy)
```
 
**描述**
 
将坐标点沿x轴和y轴方向偏移指定距离。
 
**起始版本：** 26.0.0
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| OH_Drawing_Point* point | 指向坐标点对象OH_Drawing_Point的指针。 |
| float dx | 表示在x轴上的偏移量，单位为物理像素px。正数表示往x轴正方向平移，负数表示往x轴负方向平移。 |
| float dy | 表示在y轴上的偏移量，单位为物理像素px。正数表示往y轴正方向平移，负数表示往y轴负方向平移。 |
 
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| OH_Drawing_ErrorCode | 函数返回执行错误码。 返回OH_DRAWING_SUCCESS，表示执行成功。 返回OH_DRAWING_ERROR_INCORRECT_PARAMETER，表示参数point为空。 |
 
 
  

### OH_Drawing_PointDestroy()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
void OH_Drawing_PointDestroy(OH_Drawing_Point* point)
```
 
**描述**
 
销毁坐标点对象并回收该对象占用的内存。需在[OH_Drawing_PointCreate](#oh_drawing_pointcreate)创建对象后且该对象不再使用时调用。
 
**系统能力：** SystemCapability.Graphic.Graphic2D.NativeDrawing
 
**起始版本：** 11
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| OH_Drawing_Point* point | 指向坐标点对象的指针。 |
