# ScsiPeripheralDDK

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-scsiperipheralddk
**支持设备：** PC/2in1

## 概述


**支持设备：** PC/2in1

SCSI Peripheral DDK是为开发者提供专门用于开发SCSI设备驱动程序的套件，提供了初始化DDK、释放DDK、打开关闭设备、读写设备等接口，并声明了SCSI设备驱动的开发所需的宏、枚举变量和数据结构，使用场景包括存储设备驱动开发、磁盘阵列管理等。
 
**起始版本：** 18
 
  

## 文件汇总


**支持设备：** PC/2in1
 

| 名称 | 描述 |
| --- | --- |
| scsi_peripheral_api.h | 声明用于主机侧访问SCSI设备的SCSI Peripheral DDK接口。该模块基于SCSI协议标准，通过DDK驱动服务提供SCSI设备访问能力。 |
| scsi_peripheral_types.h | 提供在SCSI Peripheral DDK（驱动开发工具包）API中使用的枚举变量、结构体和宏。 |
