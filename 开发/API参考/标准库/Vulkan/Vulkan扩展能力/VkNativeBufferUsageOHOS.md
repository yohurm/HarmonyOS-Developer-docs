# VkNativeBufferUsageOHOS

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-vulkan-vknativebufferusageohos
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct VkNativeBufferUsageOHOS {...} VkNativeBufferUsageOHOS
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

提供HarmonyOS NativeBuffer用途的说明。
 
**起始版本：** 10
 
**相关模块：** [Vulkan](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-vulkan)
 
**所在头文件：** [vulkan_ohos.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-vulkan-ohos-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| VkStructureType sType | 结构体类型，值必须为VK_STRUCTURE_TYPE_NATIVE_BUFFER_USAGE_OHOS。 |
| void* pNext | 下一级结构体指针。 |
| uint64_t OHOSNativeBufferUsage | NativeBuffer的用途说明。 |
