# InputMethod_TextConfig

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-inputmethod-inputmethod-textconfig
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct InputMethod_TextConfig InputMethod_TextConfig
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

文本输入框的文本输入行为配置结构体，用于输入框向输入法框架传递核心输入规则，输入法框架根据配置执行相应输入行为。通过配置输入属性（如输入类型、文本格式等），能够满足不同场景下的输入需求，提升用户输入体验，适用于需要精细化控制输入行为的文本输入场景。该结构体为不透明类型（opaque type），调用者不可直接访问其内部成员，仅可通过本模块提供的函数接口进行操作。
 
**起始版本：** 12
 
**相关模块：** [InputMethod](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-inputmethod)
 
**所在头文件：** [inputmethod_text_config_capi.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-inputmethod-text-config-capi-h)
 
  

## 结构体用途


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

InputMethod_TextConfig承载编辑框的配置信息，包括输入类型、回车键类型、预上屏支持、选区范围、光标信息、避让信息、窗口ID、占位符文本、abilityName等。该配置信息在[OH_TextEditorProxy_GetTextConfigFunc](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-inputmethod-text-editor-proxy-capi-h#oh_texteditorproxy_gettextconfigfunc)回调中使用，开发者需在回调内对config参数设置各配置项，输入法框架据此调整键盘布局和输入行为。
 
  

## 包含关系


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

InputMethod_TextConfig内部包含以下子结构体信息：
 
- [InputMethod_CursorInfo](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-inputmethod-inputmethod-cursorinfo)：光标信息，包括光标位置、高度等。可通过[OH_TextConfig_GetCursorInfo](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-inputmethod-text-config-capi-h#oh_textconfig_getcursorinfo)获取，返回双指针（函数内部分配内存）。
- [InputMethod_TextAvoidInfo](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-inputmethod-inputmethod-textavoidinfo)：避让信息，包括避让区域的位置和尺寸。可通过[OH_TextConfig_GetTextAvoidInfo](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-inputmethod-text-config-capi-h#oh_textconfig_gettextavoidinfo)获取，返回双指针（函数内部分配内存）。

 
相关函数：
 
- 创建/销毁函数：

  

| 函数 | 描述 |
| --- | --- |
| OH_TextConfig_Create | 创建一个新的InputMethod_TextConfig实例。 |
| OH_TextConfig_Destroy | 销毁一个InputMethod_TextConfig实例。 |
 
 
- 设置函数（Set*）：

  

| 函数 | 描述 |
| --- | --- |
| OH_TextConfig_SetInputType | 设置文本配置信息中的输入框类型。 |
| OH_TextConfig_SetEnterKeyType | 设置文本配置信息中的回车键功能类型。 |
| OH_TextConfig_SetPreviewTextSupport | 设置预上屏支持情况。 |
| OH_TextConfig_SetSelection | 设置选中文本范围。 |
| OH_TextConfig_SetWindowId | 设置所属窗口的窗口ID。 |
| OH_TextConfig_SetPlaceholder | 设置占位符文本信息。 |
| OH_TextConfig_SetAbilityName | 设置abilityName信息。 |
| OH_TextConfig_SetConsumeKeyEvents | 将编辑框是否具有完整处理字母、字符、功能等按键的能力设置到文本配置信息中。 起始版本： 26.0.0 |
 
 
- 获取函数（Get*）：

  

| 函数 | 描述 |
| --- | --- |
| OH_TextConfig_GetInputType | 获取输入框类型。 |
| OH_TextConfig_GetEnterKeyType | 获取回车键功能类型。 |
| OH_TextConfig_IsPreviewTextSupported | 获取是否支持预上屏。 |
| OH_TextConfig_GetCursorInfo | 获取光标信息（双指针，函数内部分配内存）。 |
| OH_TextConfig_GetTextAvoidInfo | 获取避让信息（双指针，函数内部分配内存）。 |
| OH_TextConfig_GetSelection | 获取选区范围信息。 |
| OH_TextConfig_GetWindowId | 获取所属窗口的窗口ID。 |
| OH_TextConfig_GetPlaceholder | 获取占位符文本信息。 |
| OH_TextConfig_GetAbilityName | 获取abilityName信息。 |
| OH_TextConfig_GetConsumeKeyEvents | 获取文本配置中编辑框是否具有完整处理字母、字符、功能等按键的能力。 起始版本： 26.0.0 |
