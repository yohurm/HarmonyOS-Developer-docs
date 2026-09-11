# ArkUI_NodeComponentEvent

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-arkui-nativemodule-arkui-nodecomponentevent
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct {...} ArkUI_NodeComponentEvent
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

定义组件回调事件的参数类型，用于在组件回调触发时传递事件相关数据，便于应用获取回调事件参数。
 
**起始版本：** 12
 
**相关模块：** [ArkUI_NativeModule](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-arkui-nativemodule)
 
**所在头文件：** [native_node.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-node-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| ArkUI_NumberValue data[MAX_COMPONENT_EVENT_ARG_NUM] | 用于存储组件回调事件的参数数据，数组元素按照回调事件定义的参数顺序排列；各事件类型的参数定义详见native_node.h相关说明。 |
