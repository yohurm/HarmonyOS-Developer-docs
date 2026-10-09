# FIDO2_CredentialRequestOptions

更新时间：2026-09-24 09:52:23

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/_f_i_d_o2___credential_request_options
**支持设备：** Phone | PC/2in1 | Tablet

## 概述


**支持设备：** Phone | PC/2in1 | Tablet

认证信息字典对象。
 
**起始版本：** 6.0.0(20)
 
**相关模块：** [FIDO2（通行密钥服务）](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/passkey)
 
**所在头文件：** [fido2_api.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/onlineauthentication_capi_header_fido2)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet
 

| 名称 | 描述 |
| --- | --- |
| FIDO2_CredentialMediationRequirement mediation | 操作是否需要用户参与。 |
| FIDO2_PublicKeyCredentialRequestOptions publicKey | publicKey凭证请求的选项。 |
 
 
  

## 结构体成员变量说明


**支持设备：** Phone | PC/2in1 | Tablet

  

### mediation


**支持设备：** Phone | PC/2in1 | Tablet

```text
FIDO2_CredentialMediationRequirement FIDO2_CredentialRequestOptions::mediation
```
 
**描述**
 
操作是否需要用户参与。
 
  

### publicKey


**支持设备：** Phone | PC/2in1 | Tablet

```text
FIDO2_PublicKeyCredentialRequestOptions FIDO2_CredentialRequestOptions::publicKey
```
 
**描述**
 
publicKey凭证请求的选项。
