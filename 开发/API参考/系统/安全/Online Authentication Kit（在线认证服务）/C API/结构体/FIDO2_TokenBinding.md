# FIDO2_TokenBinding

更新时间：2026-09-24 09:52:23

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/_f_i_d_o2___token_binding
**支持设备：** Phone | PC/2in1 | Tablet

## 概述


**支持设备：** Phone | PC/2in1 | Tablet

Token binding协议，用于客户端与依赖方通信。
 
**起始版本：** 6.0.0(20)
 
**相关模块：** [FIDO2（通行密钥服务）](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/passkey)
 
**所在头文件：** [fido2_api.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/onlineauthentication_capi_header_fido2)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet
 

| 名称 | 描述 |
| --- | --- |
| FIDO2_TokenBindingStatus status | 客户端的绑定状态。 |
| char * id | 令牌绑定标识符。 长度限制0到512。 |
 
 
  

## 结构体成员变量说明


**支持设备：** Phone | PC/2in1 | Tablet

  

### id


**支持设备：** Phone | PC/2in1 | Tablet

```text
char* FIDO2_TokenBinding::id
```
 
**描述**
 
令牌绑定标识符。
 
  

### status


**支持设备：** Phone | PC/2in1 | Tablet

```text
FIDO2_TokenBindingStatus FIDO2_TokenBinding::status
```
 
**描述**
 
客户端的绑定状态。
