# 调试Native子进程

更新时间：2026-08-29 09:41:34

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-debug-native-child-process

从26.0.0版本开始，DevEco Studio支持对[Native子进程](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/capi-nativechildprocess-development-guideline)进行调试，包括OH_Ability_StartNativeChildProcess和OH_Ability_CreateNativeChildProcess接口创建的Native子进程。
 

## 使用约束

- 支持API 26.0.0及以上版本的2in1设备。
- 通过OH_Ability_StartNativeChildProcess接口创建Native子进程时，不支持调试[隔离模式](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-child-process-h#oh_ability_childprocessconfigs_setisolationmode)（NCP_ISOLATION_MODE_ISOLATED = 1）的Native子进程。
- 通过OH_Ability_CreateNativeChildProcess接口创建Native子进程时，不支持调试[独立uid](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-native-child-process-h#oh_ability_childprocessconfigs_setisolationuid)的Native子进程。

 
 

## 调试方式

通过attach方式对Native子进程进行调试，在attach窗口中直接选择子进程进行调试。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/21/v3/eSEj7sVJS6yxnYqyuhk4tA/zh-cn_image_0000002731381977.png?HW-CC-KV=V1&HW-CC-Date=20260911T072811Z&HW-CC-Expire=86400&HW-CC-Sign=655BC533ABC979A835A23C13A4A5257567030D382538279A716391A3E13B3E81)

 
或者先attach调试主进程，再点击调试面板的![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/20/v3/O6o1jCI8RmOt4_aE6FEUWw/zh-cn_image_0000002701662750.png?HW-CC-KV=V1&HW-CC-Date=20260911T072811Z&HW-CC-Expire=86400&HW-CC-Sign=510E982C40159904A9D8F18603060B48BF15103BD83EF3E4CFED29B6E691A962)，打开attach窗口选择子进程进行调试。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/b7/v3/YNELyPNXTa6RYltWUC_OdA/zh-cn_image_0000002701822674.png?HW-CC-KV=V1&HW-CC-Date=20260911T072811Z&HW-CC-Expire=86400&HW-CC-Sign=FAAC55FE937E022B0E41F93F9CB842885F88957AA4A672BDFFBE46623113FEBE)
