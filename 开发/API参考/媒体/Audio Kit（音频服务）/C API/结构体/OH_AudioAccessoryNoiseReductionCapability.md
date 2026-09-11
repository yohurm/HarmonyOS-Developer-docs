# OH_AudioAccessoryNoiseReductionCapability

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohaudio-oh-audioaccessorynoisereductioncapability
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct OH_AudioAccessoryNoiseReductionCapability {...} OH_AudioAccessoryNoiseReductionCapability
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

定义音频配件的降噪能力。
 
**起始版本：** 26.0.0
 
**相关模块：** [OHAudio](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohaudio)
 
**所在头文件：** [native_audio_accessory_common.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-audio-accessory-common-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| uint32_t structSize | 结构体大小，单位为字节（Byte）。 调用方需初始化此字段。 系统通过此字段校验结构体大小。 |
| const OH_AudioNoiseReductionMode *supportedModes | 支持的降噪模式数组。 |
| uint32_t supportedModeCount | 支持的降噪模式数量。 |
| OH_AudioNoiseReductionMode currentMode | 设备当前降噪模式。 表示注册能力时的初始状态。 |
