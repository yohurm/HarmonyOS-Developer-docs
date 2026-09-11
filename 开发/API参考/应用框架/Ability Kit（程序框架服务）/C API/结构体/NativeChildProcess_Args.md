# NativeChildProcess_Args

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-nativechildprocess-args
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct {...} NativeChildProcess_Args
```


## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

传递给子进程的参数。

**起始版本：** 13

**相关模块：** [ChildProcess](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-childprocess)

**所在头文件：** [native_child_process.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-child-process-h)



## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable



### 成员变量


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable


| 名称 | 描述 |
| --- | --- |
| char* entryParams | 传递给子进程入口函数的参数字符串。entryParams通过IPC传输，IPC传输的数据量最大为200KB（详见约束与限制），其中部分由系统占用，建议entryParams传入数据量不超过150KB，否则可能导致创建子进程失败。 |
| struct NativeChildProcess_FdList fdList | 传递给子进程的文件描述符信息列表，文件描述符记录个数不能超过16个。子进程可通过这些文件描述符与主进程进行通信。 |
