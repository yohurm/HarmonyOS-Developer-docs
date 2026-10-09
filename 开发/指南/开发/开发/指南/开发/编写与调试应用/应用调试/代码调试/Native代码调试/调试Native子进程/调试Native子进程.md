# 调试Native子进程

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-debug-native-child-process

从26.0.0版本开始，DevEco Studio支持对[Native子进程](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/capi-nativechildprocess-development-guideline)进行调试，包括OH_Ability_StartNativeChildProcess和OH_Ability_CreateNativeChildProcess接口创建的Native子进程。
 

## 使用约束

- 支持API 26.0.0及以上版本的2in1设备。
- 通过OH_Ability_StartNativeChildProcess接口创建Native子进程时，不支持调试[隔离模式](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-child-process-h#oh_ability_childprocessconfigs_setisolationmode)（NCP_ISOLATION_MODE_ISOLATED = 1）的Native子进程。
- 通过OH_Ability_CreateNativeChildProcess接口创建Native子进程时，不支持调试[独立uid](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-child-process-h#oh_ability_childprocessconfigs_setisolationuid)的Native子进程。

 
 

## 调试方式

通过attach方式对Native子进程进行调试，在attach窗口中直接选择子进程进行调试。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/1b/v3/UO5Ab6_TTF2zoSurNnApeg/zh-cn_image_0000002731381977.png?HW-CC-KV=V1&HW-CC-Date=20261009T012804Z&HW-CC-Expire=86400&HW-CC-Sign=BC1953164849F0DA75A8753ABF6FDF92F9FC740CAECCAE15AE8B5326E3F4783A)

 
或者先attach调试主进程，再点击调试面板的![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4f/v3/XupXb5skRhSUYMmXKZ99ng/zh-cn_image_0000002701662750.png?HW-CC-KV=V1&HW-CC-Date=20261009T012804Z&HW-CC-Expire=86400&HW-CC-Sign=8B6723D70C7C63452B04B8CD80EDD3B0A68E53753CDC1286486F32E1DE1B354C)，打开attach窗口选择子进程进行调试。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/41/v3/VOOT5iQnQ3aH6HPCTZGZlw/zh-cn_image_0000002701822674.png?HW-CC-KV=V1&HW-CC-Date=20261009T012804Z&HW-CC-Expire=86400&HW-CC-Sign=A75A793D56EC2DAE2C0FE41E055D7FFE754F6BE544FE9A93ED2C9D4CAFF09678)
