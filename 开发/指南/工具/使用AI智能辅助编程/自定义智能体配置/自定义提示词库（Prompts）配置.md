# 自定义提示词库（Prompts）配置

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-prompts

## 功能介绍

从DevEco Studio 6.1.0 Beta2开始，CodeGenie支持添加和管理提示词库。如果经常针对不同的文件或代码使用某个提示词向AI提问，可以将提示词添加到常用提示词库中，在需要时通过菜单栏快速触发，从而提高开发效率。
 
 

## 操作步骤
1. 点击页面右侧菜单栏CodeGenie图标完成登录后，可以通过如下两种方式打开Prompts配置界面：

  
点击界面右上方**Settings**![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d8/v3/7J2v2FcWTWyphXce9ebU9g/zh-cn_image_0000002701663234.png?HW-CC-KV=V1&HW-CC-Date=20261009T012824Z&HW-CC-Expire=86400&HW-CC-Sign=0332723122885CF335DA79E90115C28ABB90DECF552E40082CE321A92817CCB5)按钮，选择**Prompts**。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a8/v3/Zy3-EiSpQyy3KTcdApvHFg/zh-cn_image_0000002731382461.png?HW-CC-KV=V1&HW-CC-Date=20261009T012824Z&HW-CC-Expire=86400&HW-CC-Sign=6F7D96D93083EB0CB3BFCFA0ED2C50281BA52180975655DA84FFA1AF7C6C1990)

2. 在代码编辑区右键唤醒菜单栏，点击**CodeGenie > Add New Prompts**。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/08/v3/CAE1C_t0SquL9fxzN8SzPA/zh-cn_image_0000002701663242.png?HW-CC-KV=V1&HW-CC-Date=20261009T012824Z&HW-CC-Expire=86400&HW-CC-Sign=1A09183CC89D431515FD2ACC06656D77152B6D4B143A2A0DC4BF2B3CE923DA4A)

3. 点击**Add Now**进入Prompts配置页面。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/7a/v3/YWmh0R5FT7qApWoBEIcDEA/zh-cn_image_0000002731542433.png?HW-CC-KV=V1&HW-CC-Date=20261009T012824Z&HW-CC-Expire=86400&HW-CC-Sign=AAB3B052D8F713CF9BCEC1623343234E459767FF31E7DD9129C23286A4756419)

4. 填写提示词名称、提示词内容等，点击**Save**进行保存。

  
**Title**：提示词名称，长度不超过20个字符。
5. **Prompt**：提示词的具体内容，长度不超过5000个字符。
6. **Auto-reference selected code for context**：是否自动引用所选代码作为上下文，勾选该选项后，会将选中代码和提示词一并发送给CodeGenie。
7. **Auto send prompts to AI**：是否自动发送给CodeGenie，不勾选该选项时需手动点击![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4a/v3/KwnDXJS7Tw6mQHjQOhu34w/zh-cn_image_0000002731382457.png?HW-CC-KV=V1&HW-CC-Date=20261009T012824Z&HW-CC-Expire=86400&HW-CC-Sign=444C6CFD3127B388FA26DE891A946B513F3D8F4399441CA350165641DC1E315A)发送。
8. 选中代码片或在编辑区空白位置右键，点击CodeGenie下的提示词（如安全检查），发送提示词后等待AI解析回复。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/53/v3/qgRZ-zVWRnCFdM7sj9WZpA/zh-cn_image_0000002731382451.png?HW-CC-KV=V1&HW-CC-Date=20261009T012824Z&HW-CC-Expire=86400&HW-CC-Sign=F323AEC1EBD0D3BEA805B42F7A712A360355A0FFCD5E3FD70C807BA826809125)
