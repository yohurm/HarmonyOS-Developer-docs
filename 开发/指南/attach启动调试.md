# attach启动调试

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-attach-arkts-debug

开发者也可以通过将调试程序附加到已运行的应用进行调试。
 
附加调试和调试的区别在于，附加调试可以先运行应用/元服务，然后再启动调试，或者直接启动设备上已安装的应用/元服务进行调试；而调试是直接运行应用/元服务后立即启动调试。
 

## 前提条件

当前设备上被附加调试的应用代码和本地代码一致，且已提前进行构建生成必要的sourceMap文件。
 
 

## 使用约束

附加调试不支持的场景：
 
- 本地无源码。
- 应用包名不匹配，将出现提示“**所选进程与当前项目的包名不匹配！**”，但不阻塞调试过程。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/59/v3/gpvY5D7PRTSTmvKCimtVVQ/zh-cn_image_0000002779082643.png?HW-CC-KV=V1&HW-CC-Date=20261009T012523Z&HW-CC-Expire=86400&HW-CC-Sign=E17A6E0281BDFDB502EDD3B4599F1DA0681CBE203483177286F4B22B1B86765C)


 
 

## 操作步骤
1. 在工具栏中，选择调试的设备，并单击附加调试。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/57/v3/2B-iDbnnQaOLDOSUuDfm4Q/zh-cn_image_0000002749323710.png?HW-CC-KV=V1&HW-CC-Date=20261009T012523Z&HW-CC-Expire=86400&HW-CC-Sign=046C67BB8B1B91B3F0C58332C6844EBF5B33F12C3AE41B3DB4E9BB31214ABE44)

2. 选择要调试的应用进程，若应用包名与当前工程不一致，则需勾选**显示所有进程**。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/e/v3/KO5MBOYqQB6FIz9S_FPjAA/zh-cn_image_0000002779082651.png?HW-CC-KV=V1&HW-CC-Date=20261009T012523Z&HW-CC-Expire=86400&HW-CC-Sign=3D52E5F56022B263E25EE9F7B01D63CDE450778DCC6F91485C28AE136E7D2210)

3. 选择需要使用的调试配置。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/bb/v3/-znwQq1FTBS3oae4TccRNQ/zh-cn_image_0000002749483582.png?HW-CC-KV=V1&HW-CC-Date=20261009T012523Z&HW-CC-Expire=86400&HW-CC-Sign=B382E38BB9641C75070110C7FD6F76212403A9B0BDFB3792BCEBF8793D27D9F5)

4. 选择好调试配置进行附加调试后，**调试类型**不可改变，只可在**运行/调试配置**界面修改。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/f8/v3/t1tWnOKSSx-lUFqe8j8PKg/zh-cn_image_0000002749483586.png?HW-CC-KV=V1&HW-CC-Date=20261009T012523Z&HW-CC-Expire=86400&HW-CC-Sign=38B1ECF4C06B9A8BD012156CB5576ADBC0283B0362E1AA92E9C4424D9C4F3EE7)

5. 点击**确定**开始附加调试。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/be/v3/MrHuepj0S2-Ff5kbK4RJeA/zh-cn_image_0000002778922795.png?HW-CC-KV=V1&HW-CC-Date=20261009T012523Z&HW-CC-Expire=86400&HW-CC-Sign=31B699AA87CD7C711E9D5041876A01C72D7AE62B4E33A784C98AC1ABC996ABE8)
