# oh_window_event_filter.h

更新时间：2026-09-09 06:54:05

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-oh-window-event-filter-h
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

定义窗口管理事件过滤的接口。当多模输入的事件经过窗口时，可通过过滤接口拦截事件，阻止事件向下分发。

**引用文件：** <window_manager/oh_window_event_filter.h>

**库：** libnative_window_manager.so

**系统能力：** SystemCapability.Window.SessionManager

**起始版本：** 12

**相关模块：** [WindowManager](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-windowmanager)



## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable



### 函数


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable


| 名称 | typedef关键字 | 描述 |
| --- | --- | --- |
| typedef bool (*OH_NativeWindowManager_KeyEventFilter)(Input_KeyEvent* keyEvent) | OH_NativeWindowManager_KeyEventFilter | 定义多模按键的过滤函数。 |
| WindowManager_ErrorCode OH_NativeWindowManager_RegisterKeyEventFilter(int32_t windowId,OH_NativeWindowManager_KeyEventFilter keyEventFilter) | - | 注册按键事件的过滤函数。 |
| WindowManager_ErrorCode OH_NativeWindowManager_UnregisterKeyEventFilter(int32_t windowId) | - | 取消注册窗口的按键事件过滤函数。 |
| typedef bool (*OH_NativeWindowManager_MouseEventFilter)(Input_MouseEvent* mouseEvent) | OH_NativeWindowManager_MouseEventFilter | 定义多模鼠标事件的过滤函数。 |
| WindowManager_ErrorCode OH_NativeWindowManager_RegisterMouseEventFilter(int32_t windowId,OH_NativeWindowManager_MouseEventFilter mouseEventFilter) | - | 注册鼠标事件的过滤函数。 |
| WindowManager_ErrorCode OH_NativeWindowManager_UnregisterMouseEventFilter(int32_t windowId) | - | 取消注册窗口的鼠标事件过滤函数。 |
| typedef bool (*OH_NativeWindowManager_TouchEventFilter)(Input_TouchEvent* touchEvent) | OH_NativeWindowManager_TouchEventFilter | 定义多模触摸事件的过滤函数。 |
| WindowManager_ErrorCode OH_NativeWindowManager_RegisterTouchEventFilter(int32_t windowId,OH_NativeWindowManager_TouchEventFilter touchEventFilter) | - | 注册触摸事件的过滤函数。 |
| WindowManager_ErrorCode OH_NativeWindowManager_UnregisterTouchEventFilter(int32_t windowId) | - | 取消注册窗口的触摸事件过滤函数。 |
| WindowManager_ErrorCode OH_NativeWindowManager_GetKeyEventFilter(int32_t windowId, OH_NativeWindowManager_KeyEventFilter* outKeyEventFilter) | - | 获取指定窗口注册的多模按键事件过滤函数。 |
| WindowManager_ErrorCode OH_NativeWindowManager_GetMouseEventFilter(int32_t windowId, OH_NativeWindowManager_MouseEventFilter* outMouseEventFilter) | - | 获取指定窗口注册的多模鼠标事件过滤函数。 |
| WindowManager_ErrorCode OH_NativeWindowManager_GetTouchEventFilter(int32_t windowId, OH_NativeWindowManager_TouchEventFilter* outTouchEventFilter) | - | 获取指定窗口注册的多模触摸事件过滤函数。 |




## 函数说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable



### OH_NativeWindowManager_KeyEventFilter()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef bool (*OH_NativeWindowManager_KeyEventFilter)(Input_KeyEvent* keyEvent)
```

**描述**

定义多模按键的过滤函数。

**起始版本：** 12

**参数：**


| 参数项 | 描述 |
| --- | --- |
| Input_KeyEvent* keyEvent | 多模按键事件，具体可见Input_KeyEvent，事件定义在oh_input_manager中。 |


**返回：**


| 类型 | 说明 |
| --- | --- |
| bool | 返回是否过滤该事件。返回true窗口不再往下分发，返回false表示不拦截。 |




### OH_NativeWindowManager_RegisterKeyEventFilter()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
WindowManager_ErrorCode OH_NativeWindowManager_RegisterKeyEventFilter(int32_t windowId,OH_NativeWindowManager_KeyEventFilter keyEventFilter)
```

**描述**

注册按键事件的过滤函数。

**起始版本：** 12

**参数：**


| 参数项 | 描述 |
| --- | --- |
| int32_t windowId | 需要过滤按键事件的窗口ID。 |
| OH_NativeWindowManager_KeyEventFilter keyEventFilter | 多模按键的过滤函数。 |


**返回：**


| 类型 | 说明 |
| --- | --- |
| WindowManager_ErrorCode | 函数返回的执行结果。 返回OK，表示接口调用成功。 返回INVAILD_WINDOW_ID，表示参数windowId无效。 返回WINDOW_MANAGER_ERRORCODE_INVALID_PARAM，表示参数keyEventFilter无效。 返回SERVICE_ERROR，表示窗口管理服务异常。 |




### OH_NativeWindowManager_UnregisterKeyEventFilter()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
WindowManager_ErrorCode OH_NativeWindowManager_UnregisterKeyEventFilter(int32_t windowId)
```

**描述**

取消注册窗口的按键事件过滤函数。

**起始版本：** 12

**参数：**


| 参数项 | 描述 |
| --- | --- |
| int32_t windowId | 需要取消过滤按键事件的窗口ID。 |


**返回：**


| 类型 | 说明 |
| --- | --- |
| WindowManager_ErrorCode | 函数返回的执行结果。 返回OK，表示接口调用成功。 返回INVAILD_WINDOW_ID，表示参数windowId无效。 返回SERVICE_ERROR，表示窗口管理服务异常。 |




### OH_NativeWindowManager_MouseEventFilter()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef bool (*OH_NativeWindowManager_MouseEventFilter)(Input_MouseEvent* mouseEvent)
```

**描述**

定义多模鼠标事件的过滤函数。

**起始版本：** 15

**参数：**


| 参数项 | 描述 |
| --- | --- |
| Input_MouseEvent* mouseEvent | 多模鼠标事件，具体可见Input_MouseEvent，事件定义在oh_input_manager中。 |


**返回：**


| 类型 | 说明 |
| --- | --- |
| bool | 返回是否过滤该事件。true表示过滤该事件，不会继续往下分发；false表示不过滤不拦截此事件，将会继续分发。 |




### OH_NativeWindowManager_RegisterMouseEventFilter()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
WindowManager_ErrorCode OH_NativeWindowManager_RegisterMouseEventFilter(int32_t windowId,OH_NativeWindowManager_MouseEventFilter mouseEventFilter)
```

**描述**

注册鼠标事件的过滤函数。

**起始版本：** 15

**参数：**


| 参数项 | 描述 |
| --- | --- |
| int32_t windowId | 需要过滤鼠标事件的窗口ID。 |
| OH_NativeWindowManager_MouseEventFilter mouseEventFilter | 多模鼠标事件的过滤函数。 |


**返回：**


| 类型 | 说明 |
| --- | --- |
| WindowManager_ErrorCode | 函数返回的执行结果。 返回OK，表示接口调用成功。 返回INVAILD_WINDOW_ID，表示参数windowId无效。 返回WINDOW_MANAGER_ERRORCODE_INVALID_PARAM，表示参数mouseEventFilter无效。 返回SERVICE_ERROR，表示窗口管理服务异常。 |




### OH_NativeWindowManager_UnregisterMouseEventFilter()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
WindowManager_ErrorCode OH_NativeWindowManager_UnregisterMouseEventFilter(int32_t windowId)
```

**描述**

取消注册窗口的鼠标事件过滤函数。

**起始版本：** 15

**参数：**


| 参数项 | 描述 |
| --- | --- |
| int32_t windowId | 需要取消过滤鼠标事件的窗口ID。 |


**返回：**


| 类型 | 说明 |
| --- | --- |
| WindowManager_ErrorCode | 函数返回的执行结果。 返回OK，表示接口调用成功。 返回INVAILD_WINDOW_ID，表示参数windowId无效。 返回SERVICE_ERROR，表示窗口管理服务异常。 |




### OH_NativeWindowManager_TouchEventFilter()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef bool (*OH_NativeWindowManager_TouchEventFilter)(Input_TouchEvent* touchEvent)
```

**描述**

定义多模触摸事件的过滤函数。

**起始版本：** 15

**参数：**


| 参数项 | 描述 |
| --- | --- |
| Input_TouchEvent* touchEvent | 多模触摸事件，具体可见Input_TouchEvent，事件定义在oh_input_manager中。 |


**返回：**


| 类型 | 说明 |
| --- | --- |
| bool | 返回是否过滤该事件。true表示过滤该事件，不会继续往下分发；false表示不过滤不拦截此事件，将会继续分发。 |




### OH_NativeWindowManager_RegisterTouchEventFilter()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
WindowManager_ErrorCode OH_NativeWindowManager_RegisterTouchEventFilter(int32_t windowId,OH_NativeWindowManager_TouchEventFilter touchEventFilter)
```

**描述**

注册触摸事件的过滤函数。

**起始版本：** 15

**参数：**


| 参数项 | 描述 |
| --- | --- |
| int32_t windowId | 需要过滤触摸事件的窗口ID。 |
| WindowManager_ErrorCode | 函数返回的执行结果。 返回OK，表示接口调用成功。 返回INVAILD_WINDOW_ID，表示参数windowId无效。 返回WINDOW_MANAGER_ERRORCODE_INVALID_PARAM，表示参数touchEventFilter无效。 返回SERVICE_ERROR，表示窗口管理服务异常。 |


**返回：**


| 类型 | 说明 |
| --- | --- |
| WindowManager_ErrorCode | 返回窗口管理接口的通用状态码，具体可见WindowManager_ErrorCode。 |




### OH_NativeWindowManager_UnregisterTouchEventFilter()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
WindowManager_ErrorCode OH_NativeWindowManager_UnregisterTouchEventFilter(int32_t windowId)
```

**描述**

取消注册窗口的触摸事件过滤函数。

**起始版本：** 15

**参数：**


| 参数项 | 描述 |
| --- | --- |
| int32_t windowId | 需要取消过滤触摸事件的窗口ID。 |


**返回：**


| 类型 | 说明 |
| --- | --- |
| WindowManager_ErrorCode | 函数返回的执行结果。 返回OK，表示接口调用成功。 返回INVAILD_WINDOW_ID，表示参数windowId无效。 返回SERVICE_ERROR，表示窗口管理服务异常。 |




### OH_NativeWindowManager_GetKeyEventFilter()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
WindowManager_ErrorCode OH_NativeWindowManager_GetKeyEventFilter(int32_t windowId, OH_NativeWindowManager_KeyEventFilter* outKeyEventFilter)
```

**描述**

获取指定窗口注册的多模按键事件过滤函数。

**起始版本：** 26.0.0

**参数：**


| 参数项 | 描述 |
| --- | --- |
| int32_t windowId | 窗口ID。 |
| OH_NativeWindowManager_KeyEventFilter* outKeyEventFilter | 返回已注册的多模按键事件过滤函数指针。如果窗口没有注册过滤器，*outKeyEventFilter将返回NULL。 |


**返回：**


| 类型 | 说明 |
| --- | --- |
| WindowManager_ErrorCode | 函数返回的执行结果。 返回OK，表示接口调用成功。 返回INVALID_WINDOW_ID，表示入参windowId无效。 返回WINDOW_MANAGER_ERRORCODE_INVALID_PARAM，表示入参outKeyEventFilter为NULL。 |




### OH_NativeWindowManager_GetMouseEventFilter()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
WindowManager_ErrorCode OH_NativeWindowManager_GetMouseEventFilter(int32_t windowId, OH_NativeWindowManager_MouseEventFilter* outMouseEventFilter)
```

**描述**

获取指定窗口注册的多模鼠标事件过滤函数。

**起始版本：** 26.0.0

**参数：**


| 参数项 | 描述 |
| --- | --- |
| int32_t windowId | 窗口ID。 |
| OH_NativeWindowManager_MouseEventFilter* outMouseEventFilter | 返回已注册的多模鼠标事件过滤函数指针。如果窗口没有注册过滤器，*outMouseEventFilter将返回NULL。 |


**返回：**


| 类型 | 说明 |
| --- | --- |
| WindowManager_ErrorCode | 函数返回的执行结果。 返回OK，表示接口调用成功。 返回INVALID_WINDOW_ID，表示入参windowId无效。 返回WINDOW_MANAGER_ERRORCODE_INVALID_PARAM，表示入参outMouseEventFilter为NULL。 |




### OH_NativeWindowManager_GetTouchEventFilter()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
WindowManager_ErrorCode OH_NativeWindowManager_GetTouchEventFilter(int32_t windowId, OH_NativeWindowManager_TouchEventFilter* outTouchEventFilter)
```

**描述**

获取指定窗口注册的多模触摸事件过滤函数。

**起始版本：** 26.0.0

**参数：**


| 参数项 | 描述 |
| --- | --- |
| int32_t windowId | 窗口ID。 |
| OH_NativeWindowManager_TouchEventFilter* outTouchEventFilter | 返回已注册的多模触摸事件过滤函数指针。如果窗口没有注册过滤器，*outTouchEventFilter将返回NULL。 |


**返回：**


| 类型 | 说明 |
| --- | --- |
| WindowManager_ErrorCode | 函数返回的执行结果。 返回OK，表示接口调用成功。 返回INVALID_WINDOW_ID，表示入参windowId无效。 返回WINDOW_MANAGER_ERRORCODE_INVALID_PARAM，表示入参outTouchEventFilter为NULL。 |
