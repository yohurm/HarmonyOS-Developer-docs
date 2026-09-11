# Input_DeviceListener

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-input-input-devicelistener
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct Input_DeviceListener {
    // ...
} Input_DeviceListener
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

定义一个结构体用于监听设备热插拔，该功能适用于需要实时响应输入设备连接和断开场景的应用程序，如游戏、音乐播放器等。通过监听设备热插拔事件，应用程序可以及时更新输入状态，提升用户体验，避免因设备断开导致的异常情况。
 
**起始版本：** 13
 
**相关模块：** [input](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-input)
 
**所在头文件：** [oh_input_manager.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-oh-input-manager-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| Input_DeviceAddedCallback deviceAddedCallback | 定义一个回调函数，用于接收设备热插事件。 |
| Input_DeviceRemovedCallback deviceRemovedCallback | 定义一个回调函数，用于接收设备热拔事件。 |
