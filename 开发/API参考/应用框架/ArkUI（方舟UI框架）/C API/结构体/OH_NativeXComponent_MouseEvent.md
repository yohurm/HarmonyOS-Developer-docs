# OH_NativeXComponent_MouseEvent

更新时间：2026-08-29 09:41:17（官网已下线）

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-oh-nativexcomponent-native-xcomponent-oh-nativexcomponent-mouseevent
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct {...} OH_NativeXComponent_MouseEvent
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

鼠标事件。用于在XComponent的鼠标事件回调中传递鼠标事件信息，包含触点相对于组件和屏幕的坐标、事件时间戳、鼠标动作及按键信息。
 
**起始版本：** 9
 
**相关模块：** [OH_NativeXComponent Native XComponent](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-oh-nativexcomponent-native-xcomponent)
 
**所在头文件：** [native_interface_xcomponent.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-interface-xcomponent-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| float x | 鼠标触点相对于当前组件左上角的x轴坐标。单位：vp。 |
| float y | 鼠标触点相对于当前组件左上角的y轴坐标。单位：vp。 |
| float screenX | 鼠标触点相对于XComponent所在应用屏幕左上角的x轴坐标。单位：vp。 |
| float screenY | 鼠标触点相对于XComponent所在应用屏幕左上角的y轴坐标。单位：vp。 |
| int64_t timestamp | 当前鼠标事件的时间戳。触发事件时距离系统启动的时间间隔，单位：ns。 |
| OH_NativeXComponent_MouseEventAction action | 当前鼠标事件动作。取值参考OH_NativeXComponent_MouseEventAction，包括按下、释放、移动等动作类型。 |
| OH_NativeXComponent_MouseEventButton button | 触发当前鼠标事件的按键。取值参考OH_NativeXComponent_MouseEventButton，包括左键、右键、中键、后退键、前进键等按键类型。 |
