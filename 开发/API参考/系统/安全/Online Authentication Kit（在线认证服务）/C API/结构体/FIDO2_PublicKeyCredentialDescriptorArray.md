# FIDO2_PublicKeyCredentialDescriptorArray

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/_f_i_d_o2___public_key_credential_descriptor_array
**支持设备：** Phone | PC/2in1 | Tablet

## 概述


**支持设备：** Phone | PC/2in1 | Tablet

PublicKey凭证描述符数组。
 
**起始版本：** 6.0.0(20)
 
**相关模块：** [FIDO2（通行密钥服务）](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/passkey)
 
**所在头文件：** [fido2_api.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/onlineauthentication_capi_header_fido2)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet
 

| 名称 | 描述 |
| --- | --- |
| uint32_t allowCredentiallNum | 允许凭证数目，最大为20。 |
| FIDO2_PublicKeyCredentialDescriptor * allowCredentials | 认证凭据的附加参数列表。默认值为[]。 |
 
 
  

## 结构体成员变量说明


**支持设备：** Phone | PC/2in1 | Tablet

  

### allowCredentiallNum


**支持设备：** Phone | PC/2in1 | Tablet

```text
uint32_t FIDO2_PublicKeyCredentialDescriptorArray::allowCredentiallNum
```
 
**描述**
 
允许凭证数目。
 
  

### allowCredentials


**支持设备：** Phone | PC/2in1 | Tablet

```text
FIDO2_PublicKeyCredentialDescriptor* FIDO2_PublicKeyCredentialDescriptorArray::allowCredentials
```
 
**描述**
 
认证凭据的附加参数列表。默认值为[]。
