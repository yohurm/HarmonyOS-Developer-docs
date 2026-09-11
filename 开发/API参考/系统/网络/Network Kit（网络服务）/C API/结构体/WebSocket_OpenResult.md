# WebSocket_OpenResult

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-netstack-websocket-openresult
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
struct WebSocket_OpenResult {...}
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

WebSocket客户端来自服务端连接成功的参数。
 
**起始版本：** 11
 
**相关模块：** [netstack](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-netstack)
 
**所在头文件：** [net_websocket_type.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-net-websocket-type-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| uint32_t code | WebSocket客户端连接成功码。 |
| const char *reason | WebSocket客户端连接成功原因。 |
