# FIDO2_AttestationFormatsArray

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/_f_i_d_o2___attestation_formats_array
**支持设备：** Phone | PC/2in1 | Tablet

## 概述


**支持设备：** Phone | PC/2in1 | Tablet

依赖方的数组可以使用此成员指定一个关于认证方使用的证明语句格式的首选项。
 
**起始版本：** 6.0.0(20)
 
**相关模块：** [FIDO2（通行密钥服务）](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/passkey)
 
**所在头文件：** [fido2_api.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/onlineauthentication_capi_header_fido2)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet
 

| 名称 | 描述 |
| --- | --- |
| uint32_t attestationFormatsNum | 认证凭据的附加参数列表长度。取值范围：[0, 10]。 |
| char ** attestationFormats | 认证凭据的附加参数列表。 |
 
 
  

## 结构体成员变量说明


**支持设备：** Phone | PC/2in1 | Tablet

  

### attestationFormats


**支持设备：** Phone | PC/2in1 | Tablet

```text
char** FIDO2_AttestationFormatsArray::attestationFormats
```
 
**描述**
 
认证凭据的附加参数列表。
 
  

### attestationFormatsNum


**支持设备：** Phone | PC/2in1 | Tablet

```text
uint32_t FIDO2_AttestationFormatsArray::attestationFormatsNum
```
 
**描述**
 
认证凭据的附加参数列表长度。
