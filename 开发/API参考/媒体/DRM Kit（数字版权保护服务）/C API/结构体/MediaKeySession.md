# MediaKeySession

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-drm-mediakeysession
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct MediaKeySession MediaKeySession
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

MediaKeySession结构，用于表示一个媒体密钥会话实例。MediaKeySession是DRM解密流程的核心组件，负责生成许可证请求、处理许可证响应、管理密钥状态等功能。每个MediaKeySession实例对应一个播放会话的密钥解密过程。
 
通过OH_MediaKeySystem_CreateMediaKeySession接口创建实例，通过OH_MediaKeySession_Destroy接口销毁实例。每个MediaKeySystem可创建多个MediaKeySession实例，用于处理不同的播放会话。
 
**起始版本：** 11
 
**相关模块：** [Drm](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-drm)
 
**所在头文件：** [native_drm_common.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-drm-common-h)
