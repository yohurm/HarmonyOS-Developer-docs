# 配置OHPM代理

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-environment-config

鸿蒙电脑DevEco Studio开发环境依赖于网络环境，需要连接上网络才能确保工具的正常使用。一般来说，如果使用的是个人或家庭网络，是不需要配置代理信息的，部分企业网络受限的情况下，才需要配置代理信息。可通过如下步骤进入代理配置。
 1. 进入OHPM代理设置界面。
在打开了工程的情况下，单击界面右上角**设置> 扩展 > Ohpm > 优化配置**。
2. 在欢迎页单击打开一个空目录或空文件，单击界面右上角**设置> 扩展 > Ohpm > 优化配置**。
3. 配置OHPM设置。
**OHPM仓库**：配置ohpm仓的地址信息。
```text
https://ohpm.openharmony.cn/ohpm/
```

4. **HTTP代理**：代理服务器信息。其中，**主机名**为代理服务器主机名或IP地址如下，**端口号**为代理服务器对应的端口号。如果需要配置账号密码，请使用如下格式进行配置：
```text
http://<em>u</em><em>se</em><em>r</em>:<em>password</em>@proxy.<em>proxyserver</em>.com
```

5. **启用HTTPS代理**：同步配置HTTPS代理信息。
6. 代理配置完成后，点击底部![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/0/v3/WfjDwcwQRKmKsd7lAGBteA/zh-cn_image_0000002778922757.png?HW-CC-KV=V1&HW-CC-Date=20261009T012527Z&HW-CC-Expire=86400&HW-CC-Sign=7B43666208C76CE939C39B49C944EB1CCC4A668C0E4ABBE8BF74A4ED9D793B3D)终端图标，可执行如下命令验证代理是否配置成功。执行结果如下图所示，则说明代理设置成功。
```text
ohpm info @ohos/lottie
```
 
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4e/v3/lJzoFiG9T3eVNgJBdqRxug/zh-cn_image_0000002779082611.png?HW-CC-KV=V1&HW-CC-Date=20261009T012527Z&HW-CC-Expire=86400&HW-CC-Sign=3B23BED322DD5FF47CD92F66B5C7CFBABE223F1E6B95791BA1160BA9DD9C20F0)

 
> [!NOTE]
> ohpm默认校验registry仓库地址证书。如果环境检查中ohpm registry access出现'SELF_SIGNED_CERT_IN_CHAIN'或'UNABLE_TO_VERIFY_LEAF_SIGNATURE'等证书校验错误时，请查看 FAQ-问题现象2 解决证书校验错误问题。

 
在此界面配置的代理信息将写入“/storage/Users/currentUser/.ohpm”目录下的**.ohpmrc**文件。
 1. 进入/storage/Users/currentUser/.ohpm，打开**.ohpmrc**文件。

  
> [!NOTE]
> 在文件配置前，若此路径下无.ohpmrc文件，完成OHPM代理设置后会自动生成；若此路径下存在.ohpmrc文件，完成OHPM代理设置后会生成新.ohpmrc文件，原文件以备份形式存在。

2. 修改ohpm仓库信息，示例如下所示：

  
```text
registry=https://ohpm.openharmony.cn/ohpm/
```

3. 修改ohpm代理信息，在http_proxy和https_proxy中，将user、password、proxyserver和port按照实际代理服务器进行修改。示例如下所示：

  
```text
http_proxy=http://<em>user</em>:<em>password</em>@proxy.<em>proxyserver</em>.com:<em>port</em>
https_proxy=http://<em>user</em>:<em>password</em>@proxy.<em>proxyserver</em>.com:<em>port</em>
```
 
> [!NOTE]
> 如果password中存在特殊字符，如@、#、*等符号，可能导致配置不生效，建议将特殊字符替换为ASCII码，并在ASCII码前加百分号%。常用符号替换为ASCII码对照表如下： !：%21 @：%40 #：%23 $：%24 &：%26 *：%2A

4. 将ohpm配置到环境变量中。

  
在**此电脑 > 属性 > 高级系统设置 > 高级 > 环境变量**中，在系统或者用户的PATH变量中，添加ohpm安装位置下bin文件夹的路径。默认路径为：DevEco Studio安装目录\tools\ohpm。
5. 代理配置完成后，下载并打开[命令行工具](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-command-line-tools)，执行如下命令验证网络是否正常。

  
```text
ohpm info @ohos/lottie
```
 执行结果如下图所示，则说明代理设置成功。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/b7/v3/aQiffpuVR_6sm1WJNCXm-A/zh-cn_image_0000002749323672.png?HW-CC-KV=V1&HW-CC-Date=20261009T012527Z&HW-CC-Expire=86400&HW-CC-Sign=0D4A2B8A9D0D25518A8359B3D1A22849C1FE0A49049DDD94EFD2003E661BF756)
