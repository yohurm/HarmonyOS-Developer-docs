# Print_PrintDocCallback

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-oh-print-print-printdoccallback
**支持设备：** Phone | PC/2in1 | Tablet

```text
typedef struct {...} Print_PrintDocCallback
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet

表示打印文档回调结构体。用于 C/C++ 原生应用向打印框架提供文件生成和任务状态接收能力。
 
**起始版本：** 13
 
**相关模块：** [OH_Print](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-oh-print)
 
**所在头文件：** [ohprint.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-ohprint-h)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet

  

### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet
 

| 名称 | 描述 |
| --- | --- |
| Print_OnStartLayoutWrite startLayoutWriteCb | 打印开始布局写入回调。当打印任务开始布局时，系统将调用此回调函数，要求应用写入打印文件内容。 |
| Print_OnJobStateChanged jobStateChangedCb | 打印任务状态变化回调。当打印任务状态发生变化时，系统将调用此回调函数通知应用打印任务状态变更。 |
