# notification.h

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-notification-h
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

定义通知服务API接口。
 
**引用文件：** <NotificationKit/notification.h>
 
**库：** libohnotification.so
 
**系统能力：** SystemCapability.Notification.Notification
 
**起始版本：** 13
 
**相关模块：** [NOTIFICATION](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-notification)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 函数


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | 描述 |
| --- | --- |
| bool OH_Notification_IsNotificationEnabled(void) | 查询当前应用通知使能状态。 |
 
 
  

## 函数说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### OH_Notification_IsNotificationEnabled()


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
bool OH_Notification_IsNotificationEnabled(void)
```
 
**描述**
 
查询当前应用通知使能状态。
 
**起始版本：** 13
 
**返回：**
  

| 类型 | 说明 |
| --- | --- |
| bool | true - 表示当前应用已使能通知。 false - 表示当前应用未使能通知。 |
