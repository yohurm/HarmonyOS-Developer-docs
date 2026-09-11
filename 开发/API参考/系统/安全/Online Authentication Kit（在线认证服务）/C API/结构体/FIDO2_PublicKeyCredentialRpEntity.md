# FIDO2_PublicKeyCredentialRpEntity

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/_f_i_d_o2___public_key_credential_rp_entity
**支持设备：** Phone | PC/2in1 | Tablet

## 概述


**支持设备：** Phone | PC/2in1 | Tablet

创建新凭据时依赖方的属性。
 
**起始版本：** 6.0.0(20)
 
**相关模块：** [FIDO2（通行密钥服务）](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/passkey)
 
**所在头文件：** [fido2_api.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/onlineauthentication_capi_header_fido2)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet
 

| 名称 | 描述 |
| --- | --- |
| char * id | 依赖方标识符。默认值为空。长度限制0到512。 |
| char * name | 依赖方名称。 长度限制0到512。 |
 
 
  

## 结构体成员变量说明


**支持设备：** Phone | PC/2in1 | Tablet

  

### id


**支持设备：** Phone | PC/2in1 | Tablet

```text
char* FIDO2_PublicKeyCredentialRpEntity::id
```
 
**描述**
 
依赖方标识符。
 
  

### name


**支持设备：** Phone | PC/2in1 | Tablet

```text
char* FIDO2_PublicKeyCredentialRpEntity::name
```
 
**描述**
 
依赖方名称。
