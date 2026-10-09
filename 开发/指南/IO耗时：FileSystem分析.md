# IO耗时：FileSystem分析

更新时间：2026-10-08 09:38:49

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
 
- ![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/f9/v3/-2-A9fZxTXGqEQ3CqPDjqw/zh-cn_image_0000002731542331.png?HW-CC-KV=V1&HW-CC-Date=20261009T012545Z&HW-CC-Expire=86400&HW-CC-Sign=CD2662F76A0A2CEB4A3E833A7B9B20BB85E8418B3C6E975582A16A1D52C704C1)Logical Write Bytes：逻辑写的累计次数和字节数。
- ![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/40/v3/wpjbHsrvQN2vf8ZZArYasg/zh-cn_image_0000002701663128.png?HW-CC-KV=V1&HW-CC-Date=20261009T012545Z&HW-CC-Expire=86400&HW-CC-Sign=74FE906A7DA7404D22280FF2466A086CA011387A6364BAD232F55E9B76D2595B)Logical Read Bytes：逻辑读的累计次数及字节数。
- ![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/18/v3/ZP4_AOfZStSrdIGnj-CmUQ/zh-cn_image_0000002731542317.png?HW-CC-KV=V1&HW-CC-Date=20261009T012545Z&HW-CC-Expire=86400&HW-CC-Sign=8D354F2C9B4C679ECF110570906704C82B5C04EDF5E00C376C6101A1C362BA09)Physical Write/Read Bytes：物理读写的累计次数和字节数。

 
 

框选**APP Name IO**主泳道，通过**Statistics**区域和**Details**区域查看选定时间段内的统计数据。
- Statistics区域：以进程维度展示了选定时间段内IO的统计数据，包括进程信息、IO类型、累计次数、累计字节数、最小时延、最大时延、平均时延、平均方差时延。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/f7/v3/eu1D9k_tS0qtX_htnUPMQg/zh-cn_image_0000002731542325.png?HW-CC-KV=V1&HW-CC-Date=20261009T012545Z&HW-CC-Expire=86400&HW-CC-Sign=4AB986DD50CDE1223DBC93741414CB8686AB19C177F3C737791437C14EC33A7F)

- Details区域：展示详细的IO数据，包括开始时间、进程信息、线程信息、IO类型、单次时延、单次字节数。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/da/v3/7JUM_2FGQWSy1IEETkndMw/zh-cn_image_0000002701663120.png?HW-CC-KV=V1&HW-CC-Date=20261009T012545Z&HW-CC-Expire=86400&HW-CC-Sign=48B73D805F412880F2B3699B6E7D2C84626AFABFBD1872DE66CBB0E3C51F418F)


 
 
 

主泳道包括Logical Writes、Logical Reads、Physical Writes/Reads三条子泳道。Logical Writes展示应用逻辑写的详细数据，Logical Reads展示应用逻辑读的详细数据，Physical Writes/Reads用于展示应用物理读写的详细数据。通过点选子泳道中的条块或框选子泳道，查看特定的统计数据。
 
- 点选子泳道中的条块，**Slice Detail**区域展示详情数据，包括IO的开始时间、所属进程、所属线程、类型、单次时延、单次字节数。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/b8/v3/g5uZo4K-QR6MqXTcBdE_-A/zh-cn_image_0000002731542323.png?HW-CC-KV=V1&HW-CC-Date=20261009T012545Z&HW-CC-Expire=86400&HW-CC-Sign=05F1CC0296059E867A41FDD863BD24B36D00710251EAC75AFFFFACAA372BD59F)


 
- 框选子泳道，**Details**详情区查看选定时间段内的详细数据，包括IO的开始时间、进程信息、线程信息、类型、单次时延、单次字节数。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/be/v3/-OYtxaT5T0qYh39FXbFztQ/zh-cn_image_0000002731382355.png?HW-CC-KV=V1&HW-CC-Date=20261009T012545Z&HW-CC-Expire=86400&HW-CC-Sign=D96EA45BC036DE61143A074EA3DBFFE242C4A301A8974CC2C830E5EE277B5903)


 
 

## 查看整机IO耗时

File System IO泳道显示整机的逻辑读、逻辑写、物理读写累计次数和字节数，具体统计项如下。默认显示所有的统计项，如需取消查看某项数据，可在File System IO泳道的右上角取消勾选。
 
- ![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/58/v3/PMxmxqesRtSdiTOVgYXARQ/zh-cn_image_0000002701823054.png?HW-CC-KV=V1&HW-CC-Date=20261009T012545Z&HW-CC-Expire=86400&HW-CC-Sign=93E0773A01F5B327157DBE6E84C44BD8878B1FF993216310E2C1033CC0F3CD15)Logical Write Bytes：逻辑写的累计次数和字节数。
- ![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/b1/v3/RDGfakWESYSLtd7iXJe0mw/zh-cn_image_0000002731382363.png?HW-CC-KV=V1&HW-CC-Date=20261009T012545Z&HW-CC-Expire=86400&HW-CC-Sign=7973E94EB0508BD5EB5C68C73664A9BB3CF9B4A208CE82A5D6BB9A7F023C9A94)Logical Read Bytes：逻辑读的累计次数和字节数。
- ![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/33/v3/mpWjVFRhQN2LTwSsBBaI2g/zh-cn_image_0000002701823048.png?HW-CC-KV=V1&HW-CC-Date=20261009T012545Z&HW-CC-Expire=86400&HW-CC-Sign=3B8252128A830A135BA575B93D351E0BFF23C2DE0A3D78D13ECF9735F62857E7)Physical Write/Read Bytes：物理读写的累计次数和字节数。

 
主泳道包括Logical Writes、Logical Reads、Physical Writes/Reads三条子泳道。Logical Writes子泳道展示整机逻辑写的详细数据，Logical Reads子泳道展示整机逻辑读的详细数据，Physical Writes/Reads子泳道展示整机物理读写的详细数据。
 
 

框选File System IO主泳道或子泳道，**Statistics**区域以进程维度展示选定时间段内的IO统计数据，包括进程信息、IO类型、次数、字节数、最小时延、最大时延、平均时延、平均方差时延。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/99/v3/KnImd4CuRZqrtTat2KgwfQ/zh-cn_image_0000002731542319.png?HW-CC-KV=V1&HW-CC-Date=20261009T012545Z&HW-CC-Expire=86400&HW-CC-Sign=9C1EE563DE5C9FEE097A39DBEBB97E791E0D01A0D6BB7D5F535A10ED825001D2)

 
 

单击主泳道或子泳道的Statistics区域中任意一行，右侧**More**区域中会显示详情数据，包括IO的开始时间、线程信息、单次时延、单次字节数。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/52/v3/RW0sGh73TeO-GYZ6rQO3TA/zh-cn_image_0000002701663134.png?HW-CC-KV=V1&HW-CC-Date=20261009T012545Z&HW-CC-Expire=86400&HW-CC-Sign=0050498E6FFFCB5E72CBAECA9EB8900552236079F4A7585D3286D2E60E90D173)

 
 

点选子泳道中的条块，展示条块对应时间区域的整机IO聚合数据。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ba/v3/67ebIH31TDOvojPztzJ4NA/zh-cn_image_0000002731382347.png?HW-CC-KV=V1&HW-CC-Date=20261009T012545Z&HW-CC-Expire=86400&HW-CC-Sign=1B12315D95B95A3F264B72601BCE18DC07DA9EC6ADFED1C6E7C26ADF528BF1F0)
