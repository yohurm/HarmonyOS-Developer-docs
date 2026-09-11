# FIDO2_PublicKeyAttestationCredential

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/_f_i_d_o2___public_key_attestation_credential
**支持设备：** Phone | PC/2in1 | Tablet

## 概述


**支持设备：** Phone | PC/2in1 | Tablet

定义获取注册结果结构体。
 
**起始版本：** 6.0.0(20)
 
**相关模块：** [FIDO2（通行密钥服务）](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/passkey)
 
**所在头文件：** [fido2_api.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/onlineauthentication_capi_header_fido2)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet
 

| 名称 | 描述 |
| --- | --- |
| Uint8Buff rawId | 原始凭据标识符。 |
| FIDO2_AuthenticatorAttestationResponse response | 认证器证明响应。 |
| FIDO2_AuthenticatorAttachment authenticatorAttachment | 认证器信息（FIDO2_PLATFORM表示平台，FIDO2_CROSS_PLATFORM表示漫游）。默认值为FIDO2_PLATFORM。可选。 |
| const char * id | 凭据的标识符。对于每种类型的凭据，标识符的要求都是不同的。 |
| const char * type | 此属性返回接口对象中指定凭据类型的插槽，它指定此对象所代表的凭据类型。 |
| AuthenticationExtensionsClientOutputs clientExtensionResults | 客户端扩展结果。当前版本不支持扩展，因此占位符始终为NULL，必须将clientExtensionResults键对应的值解析为{}。 |
 
 
  

## 结构体成员变量说明


**支持设备：** Phone | PC/2in1 | Tablet

  

### authenticatorAttachment


**支持设备：** Phone | PC/2in1 | Tablet

```text
FIDO2_AuthenticatorAttachment FIDO2_PublicKeyAttestationCredential::authenticatorAttachment
```
 
**描述**
 
认证器信息（平台、漫游）。默认值为FIDO2_PLATFORM。可选。
 
  

### clientExtensionResults


**支持设备：** Phone | PC/2in1 | Tablet

```text
AuthenticationExtensionsClientOutputs FIDO2_PublicKeyAttestationCredential::clientExtensionResults
```
 
**描述**
 
客户端扩展结果。当前版本不支持扩展，因此占位符始终为NULL，必须将clientExtensionResults键对应的值解析为{}。
 
  

### id


**支持设备：** Phone | PC/2in1 | Tablet

```text
const char* FIDO2_PublicKeyAttestationCredential::id
```
 
**描述**
 
凭据的标识符。对于每种类型的凭据，标识符的要求都是不同的。
 
  

### rawId


**支持设备：** Phone | PC/2in1 | Tablet

```text
Uint8Buff FIDO2_PublicKeyAttestationCredential::rawId
```
 
**描述**
 
原始凭据标识符。
 
  

### response


**支持设备：** Phone | PC/2in1 | Tablet

```text
FIDO2_AuthenticatorAttestationResponse FIDO2_PublicKeyAttestationCredential::response
```
 
**描述**
 
认证器证明响应。
 
  

### type


**支持设备：** Phone | PC/2in1 | Tablet

```text
const char* FIDO2_PublicKeyAttestationCredential::type
```
 
**描述**
 
此属性返回接口对象中指定凭据类型的插槽，它指定此对象所代表的凭据类型。
