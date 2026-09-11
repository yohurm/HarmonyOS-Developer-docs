# SecurityAudit_AuthClientConfiguration

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/devicesecurity-capi-structs-securityaudit-authclientconfiguration
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

该结构体定义了创建阻断类客户端时可配置的默认阻断策略。
 
**起始版本：** 26.0.0
 
**相关模块：** [SecurityAudit](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/devicesecurity-capi-securityaudit)
 
**所在头文件：** [security_audit.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/devicesecurity-capi-security-audit-8h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 类型 | 描述 |
| --- | --- | --- |
| timeoutAuthResult | SecurityAudit_AuthResult | 设置阻断事件响应超时时的默认阻断结果。 - SECURITY_AUDIT_AUTH_RESULT_ALLOW：超时放行 - SECURITY_AUDIT_AUTH_RESULT_DENY：超时阻断 |
