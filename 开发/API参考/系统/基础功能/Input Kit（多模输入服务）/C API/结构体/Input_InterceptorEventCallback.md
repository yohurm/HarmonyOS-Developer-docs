# Input_InterceptorEventCallback

更新时间：2026-09-14 10:46:18

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-input-input-interceptoreventcallback
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct Input_InterceptorEventCallback {...} Input_InterceptorEventCallback
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

拦截回调事件结构体，用于定义输入事件拦截所需的回调函数类型，支持拦截鼠标事件、触屏输入事件和轴事件。
 
**起始版本：** 12
 
**相关模块：** [input](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-input)
 
**所在头文件：** [oh_input_manager.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-oh-input-manager-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| Input_MouseEventCallback mouseCallback | 鼠标事件的回调函数。 |
| Input_TouchEventCallback touchCallback | 触屏输入事件的回调函数。 |
| Input_AxisEventCallback axisCallback | 轴事件的回调函数。 |
