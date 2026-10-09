# 使用HWASan检测内存错误

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-hwasan

HWASan（Hardware-Assisted Address Sanitizer）是一款类似于[Asan](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-asan)的内存错误检测工具。与ASan相比，HWASan使用的内存减少很多，因而更适合用于整个系统的清理。关于HWASan的检测原理请参考[HWASan检测原理](https://developer.huawei.com/consumer/cn/doc/best-practices/bpta-stability-address-sanitizer-principle#section187526511146)。
 
在适配过程中，若遇到应用崩溃等问题，可参考[适配常见问题](https://developer.huawei.com/consumer/cn/doc/best-practices/bpta-stability-address-sanitizer-faq)。
 

## 使用约束

- HWASan检测仅适用于AArch64架构的硬件。
- ASan、TSan、UBSan、HWASan不能同时开启，四个只能开启其中一个。

 
 

## 开启HWASan

 

### 方式一
1. 点击编辑器上方![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/38/v3/ZZJ7s4UyQXuonEst8ESsQQ/zh-cn_image_0000002778923125.png?HW-CC-KV=V1&HW-CC-Date=20261009T012532Z&HW-CC-Expire=86400&HW-CC-Sign=6084780D2983BF9B0879C326E3D67FFCF367E2D3303D98ECB4C9094B2AE41B19)按钮，在菜单中点击**Application**并选择相应模块，点击右侧![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/76/v3/hf8AglT8SnWhcl3QyAJGCQ/zh-cn_image_0000002749324036.png?HW-CC-KV=V1&HW-CC-Date=20261009T012532Z&HW-CC-Expire=86400&HW-CC-Sign=D6090C15F2C811800CE7759F75273CD88A528B2546BB5FC955C48ECA9F9133A4)按钮打开配置界面。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/3c/v3/gg_ygApHTTizZ4LOXHU2bw/zh-cn_image_0000002749483910.png?HW-CC-KV=V1&HW-CC-Date=20261009T012532Z&HW-CC-Expire=86400&HW-CC-Sign=6728FB1D7291710C4EA994DD2D81891697CCA621D87D91E8C5ABBF7601A29B31)

2. 在配置界面点击**故障分析**，勾选**硬件辅助地址检测**。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/dc/v3/HLYZlF-XSdyXyP_XdlAFBg/zh-cn_image_0000002779082973.png?HW-CC-KV=V1&HW-CC-Date=20261009T012532Z&HW-CC-Expire=86400&HW-CC-Sign=29A6CB54824592E5F51FAFA7E1FB1F32396C941471698BBD8394E25240D38279)

 
 

### 方式二
1. 修改工程目录下的AppScope/app.json5文件，添加HWASan配置开关。
```json
"hwasanEnabled": true
```

2. 在需要开启HWASan的模块级build-profile.json5中，添加构建参数开启HWASan检测插桩。
```json
"buildOption": {
  "externalNativeOptions": {
    "arguments": ["-DOHOS_ENABLE_HWASAN=ON"]
  }
```

 
 

## 使用HWASan
1. 运行或调试当前应用。
2. 当程序出现内存错误时，弹出HWASan log信息，点击信息中的链接即可跳转至引起内存错误的代码处。日志中各字段的说明请参考[HWASan日志规格](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/address-sanitizer-guidelines#hwasan日志规格)，异常检测类型请参考[HWASan异常检测类型](https://developer.huawei.com/consumer/cn/doc/best-practices/bpta-stability-hwasan-detection#section207321025115510)。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/f3/v3/v64Z2kIYSvaPQUmxGCXIaw/zh-cn_image_0000002749483908.png?HW-CC-KV=V1&HW-CC-Date=20261009T012532Z&HW-CC-Expire=86400&HW-CC-Sign=22039BDDC16A9AB4D0924F2F170929D3CF1F3A24CCB52566DFB0A9D244EF1858)
