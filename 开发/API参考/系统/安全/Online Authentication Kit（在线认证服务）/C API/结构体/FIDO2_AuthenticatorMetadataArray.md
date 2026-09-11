# FIDO2_AuthenticatorMetadataArray

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/_f_i_d_o2___authenticator_metadata_array
**支持设备：** Phone | PC/2in1 | Tablet

## 概述


**支持设备：** Phone | PC/2in1 | Tablet

描述支持的认证器数组。
 
**起始版本：** 6.0.0(20)
 
**相关模块：** [FIDO2（通行密钥服务）](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/passkey)
 
**所在头文件：** [fido2_api.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/onlineauthentication_capi_header_fido2)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet
 

| 名称 | 描述 |
| --- | --- |
| uint32_t number | 认证器数目。 |
| FIDO2_AuthenticatorMetadata * authenticators | 认证器支持的扩展。 |
 
 
  

## 结构体成员变量说明


**支持设备：** Phone | PC/2in1 | Tablet

  

### authenticators


**支持设备：** Phone | PC/2in1 | Tablet

```text
FIDO2_AuthenticatorMetadata* FIDO2_AuthenticatorMetadataArray::authenticators
```
 
**描述**
 
认证器支持的扩展。
 
  

### number


**支持设备：** Phone | PC/2in1 | Tablet

```text
uint32_t FIDO2_AuthenticatorMetadataArray::number
```
 
**描述**
 
认证器数目。
