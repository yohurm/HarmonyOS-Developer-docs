# OH_MIDICallbacks

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohmidi-oh-midicallbacks
**支持设备：** Phone | PC/2in1 | Tablet

```text
typedef struct {...} OH_MIDICallbacks
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet

客户端回调结构体，用于监听MIDI设备的热插拔事件和关键服务错误，包含设备热插拔和错误处理的回调函数指针，适用于需要在应用中实时感知MIDI设备状态变化并处理异常的场景。
 
**起始版本：** 24
 
**相关模块：** [OHMIDI](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohmidi)
 
**所在头文件：** [native_midi_base.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-midi-base-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet
 

| 名称 | 描述 |
| --- | --- |
| OH_MIDICallback_OnDeviceChange onDeviceChange | 处理设备热插拔事件的回调函数指针。 起始版本： 24 |
| OH_MIDICallback_OnError onError | 处理服务运行过程中发生的关键错误的回调函数指针。 起始版本： 24 |
