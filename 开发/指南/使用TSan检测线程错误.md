# 使用TSan检测线程错误

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-tsan

TSan（ThreadSanitizer）是一个检测数据竞争的工具。它包含一个编译器插桩模块和一个运行时库。TSan开启后，会使性能降低5到15倍，同时使内存占用率提高5到10倍。关于TSan的检测原理请参考[TSan](https://developer.huawei.com/consumer/cn/doc/best-practices/bpta-stability-tsan-detection)。
 

## 使用约束

- ASan、TSan、UBSan、HWASan不能同时开启，四个只能开启其中一个。
- TSan开启后会申请大量虚拟内存，其他申请大虚拟内存的功能（如gpu图形渲染）可能会受影响。

 
 

## 开启TSan

可通过以下两种方式开启TSan。
 
 

### 方式一
1. 点击编辑器上方![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/cc/v3/TQDXgG98RzayKkh_YZoywQ/zh-cn_image_0000002749483826.png?HW-CC-KV=V1&HW-CC-Date=20261009T012544Z&HW-CC-Expire=86400&HW-CC-Sign=DBC092C99A51156A4624D3C7EC8E8056341036EF7CCAA367C0416D07AD65202F)按钮，在菜单中点击**Application**并选择相应模块，点击右侧![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/3a/v3/6JubiYFoTLu8_NJFiX3bkg/zh-cn_image_0000002749323954.png?HW-CC-KV=V1&HW-CC-Date=20261009T012544Z&HW-CC-Expire=86400&HW-CC-Sign=A370478E515F9E3E30AC5BACD3EBB0242F48B8B3263F833D45BBB5CC6499F8E9)按钮打开配置界面。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4d/v3/VsjNCaMcQIaEvnqU4AozYA/zh-cn_image_0000002779082889.png?HW-CC-KV=V1&HW-CC-Date=20261009T012544Z&HW-CC-Expire=86400&HW-CC-Sign=09172DE91276671B72027EE0144B52420FDCFF3A1DF42335C448B062AE2420F5)

2. 在配置界面点击**故障分析**，勾选**数据竞争检测**。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/9e/v3/-1drMYE3QH2Znf7UNjq-rw/zh-cn_image_0000002749483828.png?HW-CC-KV=V1&HW-CC-Date=20261009T012544Z&HW-CC-Expire=86400&HW-CC-Sign=11135A154A5D733CA4D78FFCA33ACFBA539154A0082F15B6798D26A804234DF2)

3. 如果有引用本地library，需在library模块的build-profile.json5文件中，配置arguments字段值为“-DOHOS_ENABLE_TSAN=ON”，表示以TSan模式编译so文件。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/c4/v3/3b3CYcfETZqzbCLiU0wP6Q/zh-cn_image_0000002778923039.png?HW-CC-KV=V1&HW-CC-Date=20261009T012544Z&HW-CC-Expire=86400&HW-CC-Sign=77523A63D8F73DD49F24F030E785D31BF4B946BCF0AF7828C63FBAFBA6CCF27D)

 
 

### 方式二
1. 修改工程目录下AppScope/app.json5，添加TSan配置开关。
```text
"tsanEnabled": true
```
 
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ff/v3/aBmOnaZKQea3vw_6V5oj1Q/zh-cn_image_0000002779082887.png?HW-CC-KV=V1&HW-CC-Date=20261009T012544Z&HW-CC-Expire=86400&HW-CC-Sign=9DA2D977532F2CFC4E45A64F0EF4194BDFD554C170B515D5010771A2B5B6B30F)

2. 设置模块级构建TSan插桩。在需要开启TSan的模块中，通过添加构建参数开启TSan检测插桩，在对应模块的模块级build-profile.json5中添加命令参数：

  
```text
"arguments": "-DOHOS_ENABLE_TSAN=ON"
```
 
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/0/v3/TGm4BhO9Qf6Bx68uq4OBmQ/zh-cn_image_0000002778923041.png?HW-CC-KV=V1&HW-CC-Date=20261009T012544Z&HW-CC-Expire=86400&HW-CC-Sign=D74BAD06F068F79D4C893A9FF508C743DDD91AF6121E921BECCCAFE13B2CB893)

 
 

## 使用TSan
1. 运行或调试当前应用。
2. 当程序出现线程错误时，弹出TSan log信息，点击信息中的链接即可跳转至引起线程错误的代码处。日志中的异常检测类型请参考[TSan异常检测类型](https://developer.huawei.com/consumer/cn/doc/best-practices/bpta-stability-tsan-detection#section1180812915516)。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/2d/v3/_OvsDJv1RYWBWcFRm6y_ag/zh-cn_image_0000002749323956.png?HW-CC-KV=V1&HW-CC-Date=20261009T012544Z&HW-CC-Expire=86400&HW-CC-Sign=AC1F38DF16E31BC1B43EB83799337EE2C0BC1214AB6C7D0E6A025EBA56B68255)
