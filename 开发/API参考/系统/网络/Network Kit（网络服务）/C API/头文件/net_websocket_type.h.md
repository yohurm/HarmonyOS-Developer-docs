# net_websocket_type.h

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-net-websocket-type-h
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

定义WebSocket客户端模块的C接口需要的数据结构。
 
**引用文件：** <network/netstack/net_websocket_type.h>
 
**库：** libnet_websocket.so
 
**系统能力：** SystemCapability.Communication.NetStack
 
**起始版本：** 11
 
**相关模块：** [netstack](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-netstack)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 结构体


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| WebSocket_CloseResult | WebSocket客户端来自服务端关闭的参数。 |
| WebSocket_CloseOption | WebSocket客户端主动关闭的参数。 |
| WebSocket_ErrorResult | WebSocket客户端来自服务端连接错误的参数。 |
| WebSocket_OpenResult | WebSocket客户端来自服务端连接成功的参数。 |
| WebSocket_Header | WebSocket客户端增加header头的链表节点。 |
| WebSocket_RequestOptions | WebSocket客户端和服务端建立连接的参数。 |
| WebSocket | WebSocket客户端结构体。 |
 
 
  

### 函数


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | typedef关键字 | 描述 |
| --- | --- | --- |
| typedef void (*WebSocket_OnOpenCallback)(struct WebSocket *client, WebSocket_OpenResult openResult) | WebSocket_OnOpenCallback | websocket客户端接收open消息的回调函数定义。 |
| typedef void (*WebSocket_OnMessageCallback)(struct WebSocket *client, char *data, uint32_t length) | WebSocket_OnMessageCallback | websocket客户端接收数据的回调函数定义。 |
| typedef void (*WebSocket_OnErrorCallback)(struct WebSocket *client, WebSocket_ErrorResult errorResult) | WebSocket_OnErrorCallback | websocket客户端接收error错误消息的回调函数定义。 |
| typedef void (*WebSocket_OnCloseCallback)(struct WebSocket *client, WebSocket_CloseResult closeResult) | WebSocket_OnCloseCallback | WebSocket客户端接收close消息的回调函数定义。 |
 
 
  

## 枚举类型说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### WebSocket_ErrCode


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
enum WebSocket_ErrCode
```
 
**描述**
 
定义WebSocket请求的错误码。
 
**起始版本：** 11
  

| 枚举项 | 描述 |
| --- | --- |
| WEBSOCKET_OK = 0 | 操作成功。 |
| E_BASE = 1000 | 错误码基准值。 |
| WEBSOCKET_CLIENT_NULL = (E_BASE + 1) | WebSocket客户端为空。 |
| WEBSOCKET_CLIENT_NOT_CREATED = (E_BASE + 2) | WebSocket客户端未创建。 |
| WEBSOCKET_CONNECTION_ERROR = (E_BASE + 3) | 建立WebSocket连接时发生错误。 |
| WEBSOCKET_CONNECTION_PARSE_URL_ERROR = (E_BASE + 5) | 解析WebSocket连接参数时出错。 |
| WEBSOCKET_CONNECTION_NO_MEMORY = (E_BASE + 6) | WebSocket客户端建立连接过程中内存不足。 |
| WEBSOCKET_CONNECTION_CLOSED_BY_PEER = (E_BASE + 7) | WebSocket连接被对端关闭。 |
| WEBSOCKET_DESTROYED = (E_BASE + 8) | WebSocket连接断开。 |
| WEBSOCKET_PROTOCOL_ERROR = (E_BASE + 9) | 协议错误。 |
| WEBSOCKET_SEND_NO_MEMORY = (E_BASE + 10) | WebSocket客户端发送数据时系统内存不足。 |
| WEBSOCKET_SEND_DATA_NULL = (E_BASE + 11) | 发送数据为空。 |
| WEBSOCKET_DATA_LENGTH_EXCEEDED = (E_BASE + 12) | 发送数据长度超出限制。 |
| WEBSOCKET_QUEUE_LENGTH_EXCEEDED = (E_BASE + 13) | 发送数据队列长度超出限制。 |
| WEBSOCKET_NO_CLIENT_CONTEXT = (E_BASE + 14) | WebSocket客户端的上下文为空。 |
| WEBSOCKET_NO_HEADER_CONTEXT = (E_BASE + 15) | WebSocket客户端协议头为空。 |
| WEBSOCKET_HEADER_EXCEEDED = (E_BASE + 16) | WebSocket客户端协议头超出限制。 |
| WEBSOCKET_NO_CONNECTION = (E_BASE + 17) | WebSocket客户端未连接。 |
| WEBSOCKET_NO_CONNECTION_CONTEXT = (E_BASE + 18) | 释放WebSocket连接上下文时无相应上下文。 |
 
 
  

## 函数说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### WebSocket_OnOpenCallback()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef void (*WebSocket_OnOpenCallback)(struct WebSocket *client, WebSocket_OpenResult openResult)
```
 
**描述**
 
WebSocket客户端接收open消息的回调函数定义。
 
**起始版本：** 11
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| struct WebSocket *client | WebSocket客户端。 |
| WebSocket_OpenResult openResult | WebSocket客户端接收建立连接消息的内容。 |
 
 
  

### WebSocket_OnMessageCallback()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef void (*WebSocket_OnMessageCallback)(struct WebSocket *client, char *data, uint32_t length)
```
 
**描述**
 
WebSocket客户端接收数据的回调函数定义。
 
**起始版本：** 11
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| struct WebSocket *client | WebSocket客户端。 |
| char *data | WebSocket客户端接收的数据。 |
| uint32_t length | WebSocket客户端接收的数据长度。 |
 
 
  

### WebSocket_OnErrorCallback()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef void (*WebSocket_OnErrorCallback)(struct WebSocket *client, WebSocket_ErrorResult errorResult)
```
 
**描述**
 
WebSocket客户端接收error错误消息的回调函数定义。
 
**起始版本：** 11
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| struct WebSocket *client | WebSocket客户端。 |
| WebSocket_ErrorResult errorResult | WebSocket客户端接收连接错误消息的内容。 |
 
 
  

### WebSocket_OnCloseCallback()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef void (*WebSocket_OnCloseCallback)(struct WebSocket *client, WebSocket_CloseResult closeResult)
```
 
**描述**
 
WebSocket客户端接收close消息的回调函数定义。
 
**起始版本：** 11
 
**参数：**
  

| 参数项 | 描述 |
| --- | --- |
| struct WebSocket *client | WebSocket客户端。 |
| WebSocket_CloseResult closeResult | WebSocket客户端接收关闭消息的内容。 |
