# OH_ArkUI_UserDataSpan

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-arkui-nativemodule-oh-arkui-userdataspan
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct OH_ArkUI_UserDataSpan OH_ArkUI_UserDataSpan
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

定义用户数据Span样式，用于在富文本中为属性字符串附加自定义用户数据，以便在文本交互或自定义渲染时进行数据标识与关联。例如，在即时通讯应用中可为消息文本Span附加消息ID，在富文本编辑器中可为文本片段附加自定义样式标签等场景中使用。
 
调用[OH_ArkUI_UserDataSpan_Create](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h#oh_arkui_userdataspan_create)接口创建用户数据Span样式对象。
 
使用完毕后应调用[OH_ArkUI_UserDataSpan_Destroy](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h#oh_arkui_userdataspan_destroy)接口销毁用户数据Span样式对象。
 
创建成功后，可调用[OH_ArkUI_UserDataSpan_SetUserData](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h#oh_arkui_userdataspan_setuserdata)接口设置用户数据。
 
调用[OH_ArkUI_UserDataSpan_GetUserData](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h#oh_arkui_userdataspan_getuserdata)接口获取用户数据。
 
**起始版本：** 24
 
**相关模块：** [ArkUI_NativeModule](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-arkui-nativemodule)
 
**所在头文件：** [styled_string.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-styled-string-h)
