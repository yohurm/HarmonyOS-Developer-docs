# VkSurfaceCreateInfoOHOS

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-vulkan-vksurfacecreateinfoohos
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct VkSurfaceCreateInfoOHOS {...} VkSurfaceCreateInfoOHOS
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

包含创建Vulkan Surface时必要的参数。
 
**起始版本：** 10
 
**相关模块：** [Vulkan](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-vulkan)
 
**所在头文件：** [vulkan_ohos.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-vulkan-ohos-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| VkStructureType sType | 结构体类型，值必须为VK_STRUCTURE_TYPE_SURFACE_CREATE_INFO_OHOS。 |
| const void* pNext | 下一级结构体指针，值必须为空。 |
| VkSurfaceCreateFlagsOHOS flags | 预留的标志类型参数，值必须为0。 |
| OHNativeWindow* window | OHNativeWindow指针。 |
