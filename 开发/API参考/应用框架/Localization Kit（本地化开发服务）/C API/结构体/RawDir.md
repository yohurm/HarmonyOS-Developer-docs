# RawDir

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-rawfile-rawdir
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
typedef struct RawDir RawDir
```
  

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

RawDir表示一个已打开的rawfile目录对象，可用于遍历目录和目录下文件。通过[OH_ResourceManager_OpenRawDir](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-raw-file-manager-h#oh_resourcemanager_openrawdir)函数获取，使用完后须调用[OH_ResourceManager_CloseRawDir](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-raw-dir-h#oh_resourcemanager_closerawdir)关闭并释放。
 
**起始版本：** 8
 
**相关模块：** [rawfile](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-rawfile)
 
**所在头文件：** [raw_dir.h](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-raw-dir-h)
