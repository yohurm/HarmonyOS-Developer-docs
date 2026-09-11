# VkImportNativeBufferInfoOHOS

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-vulkan-vkimportnativebufferinfoohos
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct VkImportNativeBufferInfoOHOS {...} VkImportNativeBufferInfoOHOS
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

包含了OH_NativeBuffer结构体的指针。
 
**起始版本：** 10
 
**相关模块：** [Vulkan](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-vulkan)
 
**所在头文件：** [vulkan_ohos.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-vulkan-ohos-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| VkStructureType sType | 结构体类型。 |
| const void* pNext | 下一级结构体指针。 |
| struct OH_NativeBuffer* buffer | OH_NativeBuffer结构体的指针。 |
