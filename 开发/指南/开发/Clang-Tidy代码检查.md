# Clang-Tidy代码检查

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-clang-tidy

DevEco Studio支持通过内置的Clang-Tidy和自定义的Clang-Tidy对C/C++代码进行静态检查，以及支持配置检查规则，帮助开发者快速发现C++编码的问题。
 

## 检查规则配置

当前支持通过三种方式配置检查规则。
 
 

### 方式一：在Clang-Tidy Checks中配置
1. 在菜单栏进入**File > Settings...** （macOS系统为**DevEco Studio > Preferences/Settings...** ）> **Languages & Frameworks** > **C/C++**，勾选**Use clang-tidy via clangd to enable the following checks**选项。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/5f/v3/QqgVfUUMSX-wwge7e3lcTg/zh-cn_image_0000002731382587.png?HW-CC-KV=V1&HW-CC-Date=20261009T012759Z&HW-CC-Expire=86400&HW-CC-Sign=73104BE2F15AFE8BFCEB287065EB82CA9F4522E3F9DF0778AB5B779649C4A6D4)

2. 在选项下方添加检查规则，多条规则用英文逗号隔开，检查规则具体请参考[Clang-Tidy Checks网站](https://releases.llvm.org/19.1.0/tools/clang/tools/extra/docs/clang-tidy/checks/list.html)。

  添加检查规则时，可点击![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ee/v3/wZXg-7pbRqOoL56cJyb1DQ/zh-cn_image_0000002701823284.png?HW-CC-KV=V1&HW-CC-Date=20261009T012759Z&HW-CC-Expire=86400&HW-CC-Sign=746D04DBFB3551E3DA4FDD6EB69512C0674D83E641B7DE0C53BEECA3A7C94D85)按钮展开规则填写框，在不同行添加规则。添加完成后点击![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/3e/v3/0s9-MyvpSUmwEyP5ZkOJqA/zh-cn_image_0000002701823288.png?HW-CC-KV=V1&HW-CC-Date=20261009T012759Z&HW-CC-Expire=86400&HW-CC-Sign=ADFDF44F43653D1C1616A85E0F656AFEA6EFB0AA9446448A87D7AF004F6FBF14)按钮，多条规则会自动用英文逗号隔开。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/15/v3/tD4610MJRj2ig7nBUtHZTw/zh-cn_image_0000002731382599.png?HW-CC-KV=V1&HW-CC-Date=20261009T012759Z&HW-CC-Expire=86400&HW-CC-Sign=3F9D88290BFE790F763C334B9C472B5C3EE05C27635E811F087E3DA4430D7809)

 
 

### 方式二：在 .clang-tidy文件中配置
1. 在工程根目录中或在编辑器中搜索找到并打开 .clang-tidy文件。
2. 在**Checks**字段中添加检查规则，多条规则使用英文逗号隔开，检查规则具体请参考[Clang-Tidy Checks网站](https://releases.llvm.org/19.1.0/tools/clang/tools/extra/docs/clang-tidy/checks/list.html)。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/99/v3/aLiCejp7TWu3xNrNtq8w8Q/zh-cn_image_0000002701663374.png?HW-CC-KV=V1&HW-CC-Date=20261009T012759Z&HW-CC-Expire=86400&HW-CC-Sign=17C58B4A3104139FE16864243021B2596D10D920AD618DDFA3D904D22729954E)

 
 

### 方式三：在Inspection-checks中配置
1. 通过如下两种方法进入Inspect Code。

  
在工程目录顶部或工程目录中任意文件，单击鼠标右键选择**Inspect Code**...。
2. 在菜单栏点击**Code >Inspect Code**...。
3. 点击**Configure...> CPP > clang-tidy**，在**checks**中添加检查规则，多条规则使用英文逗号隔开，检查规则具体请参考[Clang-Tidy Checks网站](https://releases.llvm.org/19.1.0/tools/clang/tools/extra/docs/clang-tidy/checks/list.html)。

  添加检查规则时，可点击![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4e/v3/jJlzJpXBT5Wo4Eghudt3ZQ/zh-cn_image_0000002731542561.png?HW-CC-KV=V1&HW-CC-Date=20261009T012759Z&HW-CC-Expire=86400&HW-CC-Sign=72A9637AC17036293578B3C8CEEBA2B6870B4CCEEED9EE643DFD1C3FDBA35BA1)按钮展开规则填写框，在不同行添加规则。添加完成后点击![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/7e/v3/H6dyCL5-SK6pMpGfSTpQsw/zh-cn_image_0000002701823294.png?HW-CC-KV=V1&HW-CC-Date=20261009T012759Z&HW-CC-Expire=86400&HW-CC-Sign=D9CC11D61A7C3B4981184A5F851F1A619353E6A3DBC128FD36DFBB9221BCBA9C)按钮，多条规则会自动用英文逗号隔开。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/f9/v3/f7yFbPcWQOGeutdY04tUMQ/zh-cn_image_0000002731382591.png?HW-CC-KV=V1&HW-CC-Date=20261009T012759Z&HW-CC-Expire=86400&HW-CC-Sign=5D7776BA3662402A9F3449DA5B5405BF5DA7C693D98A9286594176D5EC19CAD0)

 
 

## 通过内置Clang-Tidy检查代码

使用内置Clang-Tidy进行代码自动实时检查和手动检查。
 
 

### 自动实时检查

**生效规则**
 
若勾选了**live update（show in “Current File”）**，自动实时检查时，[Clang-Tidy Checks](#section386618116187)、[.clang-tidy文件](#section158716295189)和[Inspection-checks中](#section841663417181)配置的规则均生效；若不勾选**live update（show in “Current File”）**，自动实时检查时，[Clang-Tidy Checks](#section386618116187)和 [.clang-tidy文件](#section158716295189)中配置的规则生效。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/aa/v3/2SS9a__sTEKBb-hILkC7Mw/zh-cn_image_0000002701663364.png?HW-CC-KV=V1&HW-CC-Date=20261009T012759Z&HW-CC-Expire=86400&HW-CC-Sign=F5301F8B12DE5A03A612811268292A85571B5B03AD439E90123271EBC6FADA50)

 
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

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/1c/v3/HmwolWw9T6u_T6gPkhgDFg/zh-cn_image_0000002701823282.png?HW-CC-KV=V1&HW-CC-Date=20261009T012759Z&HW-CC-Expire=86400&HW-CC-Sign=A099193E6EF61AB385A6DDC03DCD1A168E0B53C70A89F0DBD090035236EEA505)

4. 检查完成后在界面左下方可查看告警文件和告警信息，点击告警信息可跳转至具体代码位置，开发者可在界面右下方代码区和上方代码区编辑修改。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/94/v3/hftMH0WMRm2JPMosiokrSQ/zh-cn_image_0000002731382595.png?HW-CC-KV=V1&HW-CC-Date=20261009T012759Z&HW-CC-Expire=86400&HW-CC-Sign=E7D30C29CA9F07073B5D33B284AC9FC3B3FEA22D86CF1E85B2E608A8ABFB2B65)

 
 

## 通过自定义Clang-Tidy检查代码

从26.0.0版本开始，支持使用自定义Clang-Tidy进行代码自动实时检查和手动检查。
 
**生效规则**
 1. 勾选Prefer .clang-tidy files over IDE settings时，自动实时检查和手动检查时，[.clang-tidy文件中配置的规则](#section158716295189)生效。
2. 不勾选Prefer .clang-tidy files over IDE settings时，自动实时检查和手动检查时，[Inspection-checks中配置的规则](#section841663417181)生效。
 
**操作步骤**
 1. 在菜单栏进入**File > Settings...**（macOS系统为**DevEco Studio > Preferences/Settings...**）> **Languages & Frameworks** > **C/C++**，勾选**Use external Clang-Tidy instead of the built-in one**，添加clang-tidy.exe程序文件。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ec/v3/qGhYVk0OTimX7HV0VrB4IA/zh-cn_image_0000002731382593.png?HW-CC-KV=V1&HW-CC-Date=20261009T012759Z&HW-CC-Expire=86400&HW-CC-Sign=C2273871919C9FC9F2153DBBA34FFBD7B97F3E0546C6F5F0D3B29FFC47F9D2C3)


  
> [!NOTE]
> clang-tidy.exe可从DevEco Studio安装目录中获取。

2. 选择生效规则和开启实时检查。

  
进入clang-tidy界面，若勾选**Prefer .clang-tidy files over IDE settings**， [.clang-tidy文件中配置的规则](#section158716295189)生效；若不勾选**Prefer .clang-tidy files over IDE settings**，[Inspection-checks中配置的规则](#section841663417181)生效。
3. 若勾选**live update（show in “Current File”）**，会开启自动实时检查；若不勾选，需要手动检查，手动检查操作具体请参考[内置Clang-Tidy的手动检查](#section1395112325376)。
