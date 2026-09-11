# FIDO2_AuthenticatorTransportArray

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/_f_i_d_o2___authenticator_transport_array
**支持设备：** Phone | PC/2in1 | Tablet

## 概述


**支持设备：** Phone | PC/2in1 | Tablet

认证器传输方式数组。
 
**起始版本：** 6.0.0(20)
 
**相关模块：** [FIDO2（通行密钥服务）](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/passkey)
 
**所在头文件：** [fido2_api.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/onlineauthentication_capi_header_fido2)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet
 

| 名称 | 描述 |
| --- | --- |
| uint32_t transportNum | 传输方式数量。 |
| FIDO2_AuthenticatorTransport * transports | 认证器传输方式。 |
 
 
  

## 结构体成员变量说明


**支持设备：** Phone | PC/2in1 | Tablet

  

### transportNum


**支持设备：** Phone | PC/2in1 | Tablet

```text
uint32_t FIDO2_AuthenticatorTransportArray::transportNum
```
 
**描述**
 
传输方式数量。
 
  

### transports


**支持设备：** Phone | PC/2in1 | Tablet

```text
FIDO2_AuthenticatorTransport* FIDO2_AuthenticatorTransportArray::transports
```
 
**描述**
 
认证器传输方式。
