# OH_AudioAccessoryCapabilities

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohaudio-oh-audioaccessorycapabilities
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct OH_AudioAccessoryCapabilities {...} OH_AudioAccessoryCapabilities
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

定义音频配件的能力。
 
调用方需将structSize设置为sizeof(OH_AudioAccessoryCapabilities)。
 
**起始版本：** 26.0.0
 
**相关模块：** [OHAudio](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohaudio)
 
**所在头文件：** [native_audio_accessory_common.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-audio-accessory-common-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| uint32_t structSize | 结构体大小，单位为字节（Byte）。 调用方需初始化此字段。 |
| const OH_AudioStreamInfo *streamProperties | 支持的音频流配置数组。 每个条目表示采样率、采样格式和声道数的有效组合。 系统会对此数组进行深拷贝。 |
| uint32_t streamPropertyCount | 支持的音频流配置数量。 |
