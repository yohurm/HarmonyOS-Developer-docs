# native_audio_accessory_common.h

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-audio-accessory-common-h
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

声明外部音频配件设备接口的公共数据结构。
 
定义音频配件接口的公共类型。
 
**引用文件：** <ohaudio/native_audio_accessory_common.h>
 
**库：** libohaudio.so
 
**系统能力：** SystemCapability.Multimedia.Audio.Core
 
**起始版本：** 26.0.0
 
**相关模块：** [OHAudio](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohaudio)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 结构体


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | typedef关键字 | 描述 |
| --- | --- | --- |
| OH_AudioAccessoryManager | OH_AudioAccessoryManager | 声明音频配件管理器。 |
| OH_AudioAccessory | OH_AudioAccessory | 声明音频配件。 |
| OH_AudioAccessoryInputStream | OH_AudioAccessoryInputStream | 声明音频配件输入流。 |
| OH_AudioAccessoryInfo | OH_AudioAccessoryInfo | 定义音频配件的基本信息。 |
| OH_AudioAccessoryNoiseReductionCapability | OH_AudioAccessoryNoiseReductionCapability | 定义音频配件的降噪能力。 |
| OH_AudioAccessoryCapabilities | OH_AudioAccessoryCapabilities | 定义音频配件的能力。 |
 
 
  

### 枚举


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | typedef关键字 | 描述 |
| --- | --- | --- |
| OH_AudioAccessoryType | OH_AudioAccessoryType | 枚举音频配件连接类型。 |
 
 
  

## 枚举类型说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### OH_AudioAccessoryType


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
enum OH_AudioAccessoryType
```
 
**描述**
 
枚举音频配件连接类型。
 
**起始版本：** 26.0.0
  

| 枚举项 | 描述 |
| --- | --- |
| AUDIO_ACCESSORY_TYPE_BT_SPP = 1 | 蓝牙串行端口配置文件（Serial Port Profile，SPP）连接。 |
