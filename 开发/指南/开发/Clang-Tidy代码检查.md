# Clang-Tidy代码检查

更新时间：2026-08-29 09:41:34

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-clang-tidy

DevEco Studio支持通过内置的Clang-Tidy和自定义的Clang-Tidy对C/C++代码进行静态检查，以及支持配置检查规则，帮助开发者快速发现C++编码的问题。
 

## 检查规则配置

当前支持通过三种方式配置检查规则。
 
 

### 方式一：在Clang-Tidy Checks中配置
1. 在菜单栏进入**File > Settings...** （macOS系统为**DevEco Studio > Preferences/Settings...** ）> **Languages & Frameworks** > **C/C++**，勾选**Use clang-tidy via clangd to enable the following checks**选项。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/27/v3/mlPba41nRe6bjX2IkScpTA/zh-cn_image_0000002731382587.png?HW-CC-KV=V1&HW-CC-Date=20260911T072809Z&HW-CC-Expire=86400&HW-CC-Sign=9B7E77911AE3A5FB4B105BBB7CDB7DEDCC2654D92D364030D03F495762229428)

2. 在选项下方添加检查规则，多条规则用英文逗号隔开，检查规则具体请参考[Clang-Tidy Checks网站](https://releases.llvm.org/19.1.0/tools/clang/tools/extra/docs/clang-tidy/checks/list.html)。

  添加检查规则时，可点击![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4e/v3/sBCBKt41QJW8jcihv-L3-w/zh-cn_image_0000002701823284.png?HW-CC-KV=V1&HW-CC-Date=20260911T072809Z&HW-CC-Expire=86400&HW-CC-Sign=5BBD3844CC51D1F08B0C0E29E41AFE1E7B06C22E322DBC7E6775A32418FE849E)按钮展开规则填写框，在不同行添加规则。添加完成后点击![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/37/v3/viCXjoukSuC_3QE5o6QEzg/zh-cn_image_0000002701823288.png?HW-CC-KV=V1&HW-CC-Date=20260911T072809Z&HW-CC-Expire=86400&HW-CC-Sign=01F742F7E58A6FBF285C0CFAD750076265072652C3ABE9BE0E05653B8A2A5EB6)按钮，多条规则会自动用英文逗号隔开。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/99/v3/nD3Kt1vmRqKfAKxDj2vs_A/zh-cn_image_0000002731382599.png?HW-CC-KV=V1&HW-CC-Date=20260911T072809Z&HW-CC-Expire=86400&HW-CC-Sign=2C257DF96C29EBDF47B334629F493740858FFF86E59E7EB93FFAD87AC3AB2FA3)

 
 

### 方式二：在 .clang-tidy文件中配置
1. 在工程根目录中或在编辑器中搜索找到并打开 .clang-tidy文件。
2. 在**Checks**字段中添加检查规则，多条规则使用英文逗号隔开，检查规则具体请参考[Clang-Tidy Checks网站](https://releases.llvm.org/19.1.0/tools/clang/tools/extra/docs/clang-tidy/checks/list.html)。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/26/v3/WcDtAiBjRX2gPP2f4zIMPQ/zh-cn_image_0000002701663374.png?HW-CC-KV=V1&HW-CC-Date=20260911T072809Z&HW-CC-Expire=86400&HW-CC-Sign=E58BA959770ED7CCF37F8C5F3920C065903045C3084FB578F156AFF0BDBD3462)

 
 

### 方式三：在Inspection-checks中配置
1. 通过如下两种方法进入Inspect Code。

  
在工程目录顶部或工程目录中任意文件，单击鼠标右键选择**Inspect Code**...。
2. 在菜单栏点击**Code >Inspect Code**...。
3. 点击**Configure...> CPP > clang-tidy**，在**checks**中添加检查规则，多条规则使用英文逗号隔开，检查规则具体请参考[Clang-Tidy Checks网站](https://releases.llvm.org/19.1.0/tools/clang/tools/extra/docs/clang-tidy/checks/list.html)。

  添加检查规则时，可点击![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d8/v3/TxjUEbWuQ7SxzayxI5DVXw/zh-cn_image_0000002731542561.png?HW-CC-KV=V1&HW-CC-Date=20260911T072809Z&HW-CC-Expire=86400&HW-CC-Sign=571869F4E17404E3EF2E5DB24EC67769F8E821D2350BDF8C66D21093447D3BD7)按钮展开规则填写框，在不同行添加规则。添加完成后点击![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/96/v3/DmxtzttUTCK_DxrKVcA9fg/zh-cn_image_0000002701823294.png?HW-CC-KV=V1&HW-CC-Date=20260911T072809Z&HW-CC-Expire=86400&HW-CC-Sign=1C854ED375C7EC496DE9D1D427E069AA3A9EADE83916A97D77BC7FBAA4F32D28)按钮，多条规则会自动用英文逗号隔开。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/27/v3/qSUM5ZZkRMWAJwM8TIIJ3w/zh-cn_image_0000002731382591.png?HW-CC-KV=V1&HW-CC-Date=20260911T072809Z&HW-CC-Expire=86400&HW-CC-Sign=00A94933C108E764A6473CABD0AD968A763FE2A9B0CF9CA121B3D8995770E7AF)

 
 

## 通过内置Clang-Tidy检查代码

使用内置Clang-Tidy进行代码自动实时检查和手动检查。
 
 

### 自动实时检查

**生效规则**
 
若勾选了**live update（show in “Current File”）**，自动实时检查时，[Clang-Tidy Checks](#section386618116187)、[.clang-tidy文件](#section158716295189)和[Inspection-checks中](#section841663417181)配置的规则均生效；若不勾选**live update（show in “Current File”）**，自动实时检查时，[Clang-Tidy Checks](#section386618116187)和 [.clang-tidy文件](#section158716295189)中配置的规则生效。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/aa/v3/lBzZFZT4SBa6hJreviDPow/zh-cn_image_0000002701663364.png?HW-CC-KV=V1&HW-CC-Date=20260911T072809Z&HW-CC-Expire=86400&HW-CC-Sign=5CA1254EC9BBA828B6C76D2AC8FD25E884DCC2EBDAF04CB20F4803018722BA54)

 
**操作步骤**
 
代码编辑时，工具自动提示语法错误等，将鼠标放置在错误代码处会显示详细的错误信息。
 
 

### 手动检查

**生效规则**
 
手动检查时，仅[Inspection-checks中配置的规则](#section841663417181)生效。
 
**操作步骤**
 1. 通过如下两种方法，进入手动检查入口。

  
在工程目录顶部或工程目录中任意文件，单击鼠标右键选择**Inspect Code**...。
2. 在菜单栏点击**Code >Inspect Code**...。
3. 指定检查范围，如整个工程、某个模块或者具体文件，单击**Analyze**按钮执行代码检查。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/40/v3/1ZwWLH4lTvG9jPJwt6S_yg/zh-cn_image_0000002701823282.png?HW-CC-KV=V1&HW-CC-Date=20260911T072809Z&HW-CC-Expire=86400&HW-CC-Sign=1016FE75CD0833240EB050D02255BCBCB5CD9A914CE0AB1AF6F7C1AD72799424)

4. 检查完成后在界面左下方可查看告警文件和告警信息，点击告警信息可跳转至具体代码位置，开发者可在界面右下方代码区和上方代码区编辑修改。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d7/v3/pjWGUkpEQbq6OTFOHWgSDg/zh-cn_image_0000002731382595.png?HW-CC-KV=V1&HW-CC-Date=20260911T072809Z&HW-CC-Expire=86400&HW-CC-Sign=49C44F165B8D00E40E29EB3079CB79BE342FD09D8F09FCB0BF4E7742BA62E999)

 
 

## 通过自定义Clang-Tidy检查代码

从26.0.0版本开始，支持使用自定义Clang-Tidy进行代码自动实时检查和手动检查。
 
**生效规则**
 1. 勾选Prefer .clang-tidy files over IDE settings时，自动实时检查和手动检查时，[.clang-tidy文件中配置的规则](#section158716295189)生效。
2. 不勾选Prefer .clang-tidy files over IDE settings时，自动实时检查和手动检查时，[Inspection-checks中配置的规则](#section841663417181)生效。
 
**操作步骤**
 1. 在菜单栏进入**File > Settings...**（macOS系统为**DevEco Studio > Preferences/Settings...**）> **Languages & Frameworks** > **C/C++**，勾选**Use external Clang-Tidy instead of the built-in one**，添加clang-tidy.exe程序文件。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/87/v3/Sv0sIyJgQwiiNuCjCnWF1w/zh-cn_image_0000002731382593.png?HW-CC-KV=V1&HW-CC-Date=20260911T072809Z&HW-CC-Expire=86400&HW-CC-Sign=500310D621E97B0FC104AB5155EED28F57D624D81BEF24BE56F44FE60FBA18AE)


  
> [!NOTE]
> clang-tidy.exe可从DevEco Studio安装目录中获取。

2. 选择生效规则和开启实时检查。

  
进入clang-tidy界面，若勾选**Prefer .clang-tidy files over IDE settings**， [.clang-tidy文件中配置的规则](#section158716295189)生效；若不勾选**Prefer .clang-tidy files over IDE settings**，[Inspection-checks中配置的规则](#section841663417181)生效。
3. 若勾选**live update（show in “Current File”）**，会开启自动实时检查；若不勾选，需要手动检查，手动检查操作具体请参考[内置Clang-Tidy的手动检查](#section1395112325376)。
