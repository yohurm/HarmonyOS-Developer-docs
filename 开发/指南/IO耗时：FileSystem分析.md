# IO耗时：FileSystem分析

更新时间：2026-09-08 02:53:31

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-profiler-filesystem

## 功能介绍

应用在开发过程中，可能因为线程频繁切换、磁盘负载高等情况导致文件系统IO耗时问题。从26.0.0版本开始，DevEco Profiler新增FileSystem模板，可以结合应用逻辑IO和物理IO的读写耗时、整机（设备上所有应用）逻辑IO和物理IO的读写耗时等情况，定位IO耗时问题。
 
FileSystem模板支持的泳道包括：APP Name IO、File System IO、Callstack、Frame。本文介绍APP Name IO、File System IO泳道，其他泳道的详细信息请参考对应模板内容。
 
- Callstack泳道的介绍请参考[基础耗时：Time分析](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-insight-session-time)。
- Frame泳道的介绍请参考[Frame分析](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-insight-session-frame)。

 
> [!NOTE]
> 任务分析前，需创建FileSystem分析任务并录制相关数据，操作方法可参考 性能问题定位：深度录制 ，或在 会话区 选择 Open File ，导入历史数据。 仅应用触发逻辑IO读写时，Callstack泳道才会采集数据。

 
 

## 约束与限制

仅支持2in1设备。
 
 

## 查看应用IO耗时

APP Name IO泳道显示调测应用的逻辑读、逻辑写、物理读写的累计次数和字节数，具体统计项如下。默认显示所有的统计项，如需取消查看某项数据，可在APP Name IO泳道的右上角取消勾选。
 
- ![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/11/v3/szOYXl3ORO-Qiqz6QGhhBw/zh-cn_image_0000002731542331.png?HW-CC-KV=V1&HW-CC-Date=20260911T072348Z&HW-CC-Expire=86400&HW-CC-Sign=C606F052B8CA30096669B1E0811F3FB01A1D0BC81F4B1D4205562DAB7C729DB5)Logical Write Bytes：逻辑写的累计次数和字节数。
- ![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a2/v3/i6i2dw3iR-mbjnpy1Nbp6Q/zh-cn_image_0000002701663128.png?HW-CC-KV=V1&HW-CC-Date=20260911T072348Z&HW-CC-Expire=86400&HW-CC-Sign=AEA4C9F99619CE425DE3E2A72C1EB49B2830F3C0436B14C9F3339A33123A1325)Logical Read Bytes：逻辑读的累计次数及字节数。
- ![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/5d/v3/tByX-0FCRuacu-akAzW6fw/zh-cn_image_0000002731542317.png?HW-CC-KV=V1&HW-CC-Date=20260911T072348Z&HW-CC-Expire=86400&HW-CC-Sign=472C7358C17AA87838E786BE974DC6989BBF771400242C5DD2971C46D80C48ED)Physical Write/Read Bytes：物理读写的累计次数和字节数。

 

 
框选**APP Name IO**主泳道，通过**Statistics**区域和**Details**区域查看选定时间段内的统计数据。
- Statistics区域：以进程维度展示了选定时间段内IO的统计数据，包括进程信息、IO类型、累计次数、累计字节数、最小时延、最大时延、平均时延、平均方差时延。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/8b/v3/yHV7OIMYQeW0hjslK1wqZg/zh-cn_image_0000002731542325.png?HW-CC-KV=V1&HW-CC-Date=20260911T072348Z&HW-CC-Expire=86400&HW-CC-Sign=7AEC592B3412A77C7C6664FE77CE05CB4FABAD8FC2A004AB91EAF94BE784A6D2)

- Details区域：展示详细的IO数据，包括开始时间、进程信息、线程信息、IO类型、单次时延、单次字节数。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/e0/v3/iU47crelR0uR9n4HuJWBpg/zh-cn_image_0000002701663120.png?HW-CC-KV=V1&HW-CC-Date=20260911T072348Z&HW-CC-Expire=86400&HW-CC-Sign=825C9C1218B4282A716B0639A0EA0D26E67B565CD2D1595F68D5501ACF296A7C)


 
 

 
主泳道包括Logical Writes、Logical Reads、Physical Writes/Reads三条子泳道。Logical Writes展示应用逻辑写的详细数据，Logical Reads展示应用逻辑读的详细数据，Physical Writes/Reads用于展示应用物理读写的详细数据。通过点选子泳道中的条块或框选子泳道，查看特定的统计数据。
 
- 点选子泳道中的条块，**Slice Detail**区域展示详情数据，包括IO的开始时间、所属进程、所属线程、类型、单次时延、单次字节数。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d3/v3/LQlRU_JrRGivBuuaGyhBnw/zh-cn_image_0000002731542323.png?HW-CC-KV=V1&HW-CC-Date=20260911T072348Z&HW-CC-Expire=86400&HW-CC-Sign=44DA4187BA0F28A69ABC22C6090E3658665221B3242D261DF4AC315B4411EA96)


 
- 框选子泳道，**Details**详情区查看选定时间段内的详细数据，包括IO的开始时间、进程信息、线程信息、类型、单次时延、单次字节数。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/3d/v3/YJT69AJAQpKMSxnSkdwqTA/zh-cn_image_0000002731382355.png?HW-CC-KV=V1&HW-CC-Date=20260911T072348Z&HW-CC-Expire=86400&HW-CC-Sign=4DFF1489E4B2CB8FE1CBBBD9CFD2DF8415A0DF3AA2335670DF2CA3F0F77F9DCD)


 
 

## 查看整机IO耗时

File System IO泳道显示整机的逻辑读、逻辑写、物理读写累计次数和字节数，具体统计项如下。默认显示所有的统计项，如需取消查看某项数据，可在File System IO泳道的右上角取消勾选。
 
- ![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d1/v3/a6M7_gb2SjyhMSksWnRzZA/zh-cn_image_0000002701823054.png?HW-CC-KV=V1&HW-CC-Date=20260911T072348Z&HW-CC-Expire=86400&HW-CC-Sign=C7AEF77E0F31569E16928C59F3EDBF2B5BE0139A4F57E378E493D2F4D6059137)Logical Write Bytes：逻辑写的累计次数和字节数。
- ![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/77/v3/Y06DERl9QvGY__ohvmPpPA/zh-cn_image_0000002731382363.png?HW-CC-KV=V1&HW-CC-Date=20260911T072348Z&HW-CC-Expire=86400&HW-CC-Sign=0BA82A81B60DE48E7B80237DD6623E3246A5A3267BF4A191F0155B2204DA7C8A)Logical Read Bytes：逻辑读的累计次数和字节数。
- ![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/80/v3/0hSEYwa5QFGkeLVRqYxCbw/zh-cn_image_0000002701823048.png?HW-CC-KV=V1&HW-CC-Date=20260911T072348Z&HW-CC-Expire=86400&HW-CC-Sign=CB3302A8A5F5B205871C45B0D98491C7A74914B1F7EB407E3469683F47FA2C11)Physical Write/Read Bytes：物理读写的累计次数和字节数。

 
主泳道包括Logical Writes、Logical Reads、Physical Writes/Reads三条子泳道。Logical Writes子泳道展示整机逻辑写的详细数据，Logical Reads子泳道展示整机逻辑读的详细数据，Physical Writes/Reads子泳道展示整机物理读写的详细数据。
 

 
框选File System IO主泳道或子泳道，**Statistics**区域以进程维度展示选定时间段内的IO统计数据，包括进程信息、IO类型、次数、字节数、最小时延、最大时延、平均时延、平均方差时延。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4a/v3/8Y_NiaIsQAeInoqfX4yUQg/zh-cn_image_0000002731542319.png?HW-CC-KV=V1&HW-CC-Date=20260911T072348Z&HW-CC-Expire=86400&HW-CC-Sign=AD0C369CE7A2E5489AFAB44C9CBDA1A497ABF419FACB4A6FDDCB5E036A22847E)

 

 
单击主泳道或子泳道的Statistics区域中任意一行，右侧**More**区域中会显示详情数据，包括IO的开始时间、线程信息、单次时延、单次字节数。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/84/v3/4t3gufywSxujXozxTIMFSw/zh-cn_image_0000002701663134.png?HW-CC-KV=V1&HW-CC-Date=20260911T072348Z&HW-CC-Expire=86400&HW-CC-Sign=1FD6B4756107CE06711D3BCF877C124C9EC016FC899E10BB5CAB097638AA2F21)

 

 
点选子泳道中的条块，展示条块对应时间区域的整机IO聚合数据。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/85/v3/Up8mN2XURkyaAzbUWqG5hg/zh-cn_image_0000002731382347.png?HW-CC-KV=V1&HW-CC-Date=20260911T072348Z&HW-CC-Expire=86400&HW-CC-Sign=D48F2D8B5F70D71C0B9BCB7389448BF16EF8DF594A9881E7C14BD5A729D565C5)
