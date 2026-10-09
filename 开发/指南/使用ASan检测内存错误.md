# 使用ASan检测内存错误

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-asan

为追求C/C++的极致性能，编译器和OS运行框架不会对内存操作进行安全检测。针对该场景，鸿蒙电脑DevEco Studio集成ASan（Address-Sanitizer）为开发者提供面向C/C++的地址越界检测能力，并通过FaultLog展示错误的堆栈详情及导致错误的代码行。关于ASan的检测原理请参考[ASan检测原理](https://developer.huawei.com/consumer/cn/doc/best-practices/bpta-stability-address-sanitizer-principle#section159561141247)。
 

## 使用约束

- 如果应用内的任一模块开启ASan，那么entry模块需同时开启ASan。如果entry模块未开启ASan，该应用在启动时将闪退，出现CPP Crash报错。
- ASan、TSan、UBSan、HWASan不能同时开启，只能开启其中一个。

 
 

## 开启ASan

可通过以下两种方式开启ASan。
 
 

### 方式一
1. 点击编辑器上方![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/30/v3/a05G7B7qQyqpsEGRD7QL9Q/zh-cn_image_0000002778923117.png?HW-CC-KV=V1&HW-CC-Date=20261009T012523Z&HW-CC-Expire=86400&HW-CC-Sign=336A7F5E62E02225061881B084355EBA0F50238299A6342C2351E45497F3F1A3)按钮，在菜单中点击**Application**并选择相应模块，点击右侧![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/2f/v3/zm3zc0LMQgWkGy2QQqhD1A/zh-cn_image_0000002778923115.png?HW-CC-KV=V1&HW-CC-Date=20261009T012523Z&HW-CC-Expire=86400&HW-CC-Sign=457A650DEB85BBBB82BC170472D81F617ED9EAD54DCBE632E35F579C509D32AE)按钮打开配置界面。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a9/v3/enQGsE-RQDuwMn36krlJRg/zh-cn_image_0000002749324030.png?HW-CC-KV=V1&HW-CC-Date=20261009T012523Z&HW-CC-Expire=86400&HW-CC-Sign=5D2989284ABADE1F84893E87D8AA8FBDB9493900C90C87F003CCADBC06EA3F03)

2. 在配置界面点击**故障分析**，勾选**地址越界检测**。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ab/v3/UgDLxeVYRKmDTKu9reU6oQ/zh-cn_image_0000002779082965.png?HW-CC-KV=V1&HW-CC-Date=20261009T012523Z&HW-CC-Expire=86400&HW-CC-Sign=72C5E011B02F75B45A98CF473F8D1045FFB335516D2C6010E8F582802D633455)

3. 如果有引用本地library，需在library模块的build-profile.json5文件中，配置arguments字段值为“-DOHOS_ENABLE_ASAN=ON”，表示以ASan模式编译so文件。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/cd/v3/tefWawg2QcaoVS7EtuU-Qw/zh-cn_image_0000002779082963.png?HW-CC-KV=V1&HW-CC-Date=20261009T012523Z&HW-CC-Expire=86400&HW-CC-Sign=C9513210EA9DFBDCD55AE202B3558D8248CBE40CA39E68B15CBF82F911F1C861)

 
 

### 方式二
1. 修改工程目录下AppScope/app.json5，添加ASan配置开关。
```text
"asanEnabled": true
```
 
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ba/v3/S9LJeplBQH-xB75OoYrrMg/zh-cn_image_0000002779082967.png?HW-CC-KV=V1&HW-CC-Date=20261009T012523Z&HW-CC-Expire=86400&HW-CC-Sign=40D8A560AA2D035690EA4BB8CC8BA2BE3BE4FFF8D97B2C2B41CF7524B63516F3)

2. 设置模块级构建ASan插桩。在需要开启ASan的模块中，通过添加构建参数开启ASan检测插桩，在对应模块的模块级build-profile.json5中添加命令参数：

  
```text
"arguments": "-DOHOS_ENABLE_ASAN=ON"
```
 
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/6a/v3/Cxt4tNGtRFO0rZKKKMK96w/zh-cn_image_0000002749324028.png?HW-CC-KV=V1&HW-CC-Date=20261009T012523Z&HW-CC-Expire=86400&HW-CC-Sign=5A6C8E5D29DDB03F9B21B83206D2E8B357F6FC014AC4CADA62B517240FEEC00A)


  
> [!NOTE]
> 该参数未配置不会报错，但是除包含malloc和free函数等少数内存错误外，出现其他需要插桩检测的内存错误时，ASan无法检测到错误。

 
 

## 配置参数（可选）

ASAN_OPTIONS用于在运行时配置ASan的行为，包括设置检测级别、输出格式、内存错误报告的详细程度等。ASAN_OPTIONS支持在app.json5中配置，也支持在运行/调试配置中配置。app.json5的优先级更高，即两种方式都配置后，以app.json5中的配置为准。关于ASAN_OPTIONS的配置方式和常用参数请参考[配置参数](https://developer.huawei.com/consumer/cn/doc/best-practices/bpta-stability-asan-detection#section1496994494018)。
 
 

## 使用ASan
1. 运行或调试当前应用。
2. 当程序出现内存错误时，弹出ASan log信息，点击信息中的链接即可跳转至引起内存错误的代码处。日志中各字段的说明请参考[ASan日志规格](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/address-sanitizer-guidelines#asan日志规格)，异常检测类型请参考[ASan异常检测类型](https://developer.huawei.com/consumer/cn/doc/best-practices/bpta-stability-asan-detection#section12508111110451)。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/83/v3/QJBEw0lPRlihdiB6lWCarA/zh-cn_image_0000002749483900.png?HW-CC-KV=V1&HW-CC-Date=20261009T012523Z&HW-CC-Expire=86400&HW-CC-Sign=D64828084EF8E5A2DB8F54A8583B298D8057E4944B9E0111FBFAB5AF73DB8467)
