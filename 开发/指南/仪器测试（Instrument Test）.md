# 仪器测试（Instrument Test）

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-instrument-test

鸿蒙电脑DevEco Studio支持应用/元服务测试框架，提供测试用例执行能力，提供用例编写基础接口，输出测试结果，支持用户开发简洁易用的自动化测试脚本，支持代码覆盖率统计。当前支持Instrument Test，测试用例存放在ohosTest测试目录下，需要运行在设备上。Instrument Test支持ArkTS/JS语言。
 
> [!NOTE]
> 覆盖率测试不支持开启混淆。

 

## 创建ArkTS测试用例
1. 手动在**ohosTest **>** ets** > **test**文件夹下创建测试文件，文件名以.test.ets结尾，具体测试代码需要开发者根据业务逻辑进行开发，具体请参考[自动化测试框架使用指导](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/arkxtest-guidelines)。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/cd/v3/GJLxYS4-QdOTK4i-A4X62g/zh-cn_image_0000002749324006.jpg?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=A6B7DE18F57F89EFF028DD4472F85B9E8370FF76FA7BCF55B790F66377110DE4)

2. 在List.test.ets文件中添加创建的用例类，例如用例类abilityTest。
```text
import abilityTest from <span style="color: rgb(255,0,170);">'./Ability.test'</span><span style="color: rgb(181,106,1);">;</span>

export default function <span style="color: rgb(0,0,255);">testsuite</span><span style="color: rgb(0,0,255);">() </span><span style="color: rgb(255,0,170);">{</span>
  abilityTest<span style="color: rgb(0,0,255);">()</span><span style="color: rgb(181,106,1);">;</span>
<span style="color: rgb(255,0,170);">}</span>
```
 
> [!NOTE]
> 手动创建的工程或历史工程，ohosTest > ets > test文件夹下所有文件的文件名必须以.test.ets结尾。 测试文件名称应保持唯一性，并且不能使用逗号、横线、空格以及\ / : * ? “”< > | （）&等特殊字符。 首次在HarmonyOS设备上运行UI测试框架需要使用命令“hdc -n shell param set persist.ace.testmode.enabled 1”使能UITest测试能力。

 
 

## 运行测试用例

 

### 运行模式

使用DevEco Studio运行测试用例前，需要将设备与电脑进行连接，将工程编译成带签名信息的HAP，再安装到真机设备上运行，具体请参考[应用/元服务运行](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-run-device)。
 
可以采用运行工程目录（test）、测试文件（如Ability.test.ets）、测试套件（describe）、测试方法（it）的方式来运行测试用例：
 
- 在工程目录中，单击**右键 > 运行 '测试文件名称'**，执行测试。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/74/v3/zApe2Pu1Rm-Q47g7P6Rhgw/zh-cn_image_0000002749323990.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=13232288BAD99D3FD3888D3674DA5B5EA6E5E2EAE473A97C8D0200A2674CFC29)

- 打开测试文件，单击测试套件左侧按钮。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/dc/v3/ELXruenaSa6tPYFACMu9GA/zh-cn_image_0000002779082925.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=5B1343136FB61428F8ABE7BBBBB4528BDA23A583B8314F2888D226F0C4303FA4)

- 如果要根据自定义的配置执行Instrument Test，在[创建测试用例运行任务](#section1631610401035)后，点击DevEco Studio的
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/30/v3/iJ_TlsU6SX2gNiB6RSGyAw/zh-cn_image_0000002779082939.jpg?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=D111F3826186ADA55EB4D94E44065C690B09B7C2E4A1FDE9900460DE994ECB72)
图标选择测试任务，然后单击右侧的
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/0/v3/olVPo0Z5TUCV5rd6MgOYKQ/zh-cn_image_0000002749483880.jpg?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=E120302A73717ACC6F6219466977B4117437691BD568C391A93DA9DF8E6AD5E3)
按钮执行Instrument Test。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/57/v3/CLzdy5seRsKlf6wbYyyU4Q/zh-cn_image_0000002749324004.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=1FDAC1E39D0DCADBCDA0B54D3D4E3ABB0F7975327952062D025AFEE28F3152FF)


 
执行完测试任务后，查看测试结果。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a7/v3/o6Wc9SWMT5u8yO0F6h2kxA/zh-cn_image_0000002749483860.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=A2D950DCAC0D385BE7695B59871EBCCCF27D169D2D3856C4CE6EC946672C30E2)

 
 

### 调试模式

调试模式相比运行模式增加了断点管理功能。在断点命中时，可以选择单步执行、步入步出、进入下个断点等方式进行调试，另外可以使用线程堆栈可视化、变量和表达式可视化功能，快速定位问题。
 
以文件级别为例，在添加断点之后，有两种方式启动测试：
 
- 方式一：在工程目录中，选中文件，单击**右键 > 调试 '测试文件名称'**，以调试模式执行测试任务。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/25/v3/TiIn5vdlSAes4ipCmOQ2fA/zh-cn_image_0000002749323986.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=9792FA91E55117527F20C0F61C0B961A54942F1C3FEB28F9A4E04A79290BB41C)

- 方式二：点击右上角![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d6/v3/hpuDtk51R_yEK-P3icrlmg/zh-cn_image_0000002778923097.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=A0A90843E518FE457C5A63F8598800E370F4673BA7FADB0FFB01B860EABD28AE)图标执行测试。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/eb/v3/vF9dZMcqSbGMKWL_cB2ZmA/zh-cn_image_0000002779082923.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=2B57C57DED2D553A0A546412F62901FC8A65CF2AD2DD28D7D5B977CE2C2B8E57)


 
在断点命中时，下方将出现调试器窗口。开发者可在该窗口中进行断点管理与基础调试能力的可视化操作，在断点命中时可查看当前线程的变量和堆栈信息。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/fd/v3/u6ZPrKHlQH-FTkk7c6SUvw/zh-cn_image_0000002779082921.jpg?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=7CB80F7984B851D739B82D2551F79F0822FD6DB42B424091B6DDAD46B7E3AE15)

 
断点命中时，在调试窗口中将出现调试模式特有功能，如计算表达式、添加变量监视等。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/31/v3/1lzr4YMqSRub2e5L4qXtkQ/zh-cn_image_0000002749324000.jpg?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=6CC621496E9ABDDB3A7AB838102C0D026FA16F258E90E2EDF05CF8BC2D4747BF)

 
在跳出所有断点后，测试结束，与运行模式相同，在测试窗口查看测试结果。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a6/v3/WKhU8qB_TDyu1k1YH9T1dw/zh-cn_image_0000002779082931.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=81DCEC9C0553F6FAD33A2F7745DF1A90995349562E1872D84CD11F9B1FC85204)

 
> [!NOTE]
> DevEco Studio支持设置调试代码类型，具体请参考 设置调试代码类型 。

 
 

### 覆盖率统计模式

> [!NOTE]
> 源码文件的命名不可为“test.ets”、“xx.test.ets”、“test.ts”和“xx.test.ts”，该命名的文件不会生成报告。

 
在Instrument Test运行的基础上支持代码覆盖率统计。
 
可以采用运行工程目录（test）、测试文件（如Ability.test.ets）、测试套件（describe）、测试方法（it）的方式来启动代码覆盖率的统计。
 
以文件级别为例，有两种方式启动测试：
 
- 方式一：在工程目录中，选中文件，单击**右键 > 使用覆盖率运行 '测试文件名称' **，执行测试。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/1f/v3/tM4kL_jKSFW9VvKGwpb-KQ/zh-cn_image_0000002749483864.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=7554E05E7C0EC8748725B3B0433C16590441E667DA954B55F027FC2C3C41C7CE)

- 方式二：点击右上角
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/73/v3/SIqJ7X2IS5-xl755i3M_og/zh-cn_image_0000002779082943.jpg?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=75583F6CFA6E91A23FB53E14FB685B1B4250A8BC2474A6D81619F82FCCF63B4E)
图标执行测试。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/63/v3/NvBuEkwRTA6nucv75b1eoA/zh-cn_image_0000002749483872.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=E34E6DED82DD8C1F1FF533433B72418D1609FF85EB194F2CBE483858894E3853)


 
启动测试后，进行编译构建，构建结束后自动拉起测试窗口，测试任务结束后，窗口中会打印测试报告的路径。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/68/v3/rSjNBd1BR0uNV3BKiN31qA/zh-cn_image_0000002779082941.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=8BB7FA033887815A587C5CEBB3682C8300992F62BFD46AB2612BAB7F2F9111A0)

 
在本地找到报告后鼠标右键快速查看，打开报告，查看ArkTS代码覆盖率详情。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/72/v3/3rGBnfhXSjumwh9e7xOs8w/zh-cn_image_0000002749323998.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=10A1B51C2832DC2B66CCC0AED4A0565D7091F3A525CD9FD8840931562599B6DB)

 
 

## （可选）自定义测试用例运行任务

默认情况下，测试用例可直接运行，如果需要自定义测试用例运行任务，可通过如下方法进行设置。
 1. 点击编辑器顶部
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/c5/v3/RSPyqQNAQDK2vHeBHh0iqw/zh-cn_image_0000002778923073.jpg?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=B34379E3B160A13625FBEF42D89A387E31C1B43A20D06F7AE48FA685ED5D3CD0)
图标**，**选择**管理配置**进入配置管理界面。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4d/v3/0iJ0O1lkTbaFZTRfx-0LFA/zh-cn_image_0000002779082937.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=0CDAC2434974ADA81181E720F692A178459303E5E95FD95E7FA7F1E3C4EC4377)

2. 在**管理配置**界面，点击
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/1f/v3/ARKtdlzYTbOFHpBMBOm6qA/zh-cn_image_0000002749323988.jpg?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=2AAFC1E8EB3A73FE6F1A1886920ADF836DCF7D78CABE73BA6BB0AF7F6714CC90)
按钮，在弹出的下拉菜单中，点击**Test**，输入名称后点击右侧![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/2a/v3/WozQ7aaUTMSVL4Mvr46QTg/zh-cn_image_0000002778923087.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=1AD84CCA2ACC2A597E6A20C0341F8F4B3E5769ABB73692D5E175978A7652CCD2)图标打开配置面板。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/76/v3/BfvlpXtFRwCyTru4c3a5Ag/zh-cn_image_0000002779082929.jpg?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=F3BB4C75F1CD388AE152C769C836746109E30341FF32636D481B5381A0A4CDF7)

3. 根据实际情况，配置Instrument Test的运行参数。
如果模块依赖共享包，请提前设置HAP安装方式，勾选**保留应用数据**，则表示采用覆盖安装方式，保留应用/元服务缓存数据。
4. 如果工程中HAP/HSP模块直接依赖其他HSP模块（如entry模块依赖HSP模块）或间接依赖其他模块（如entry模块依赖HAR模块，HAR又依赖HSP模块），在测试阶段需要同时安装模块包及其所有依赖模块的包到设备中。此时，可以勾选**自动依赖**，测试时会自动将所有依赖的模块都安装到设备上。该选项默认勾选。
5. 如果不涉及UI测试，勾选**Only OhosTest Package**，则只会推送OhosTest测试包到设备上，不会推送HAP/HSP包，可以缩短推包时间。
 
 

### 使用过滤条件筛选待运行的测试用例
1. 在用例编写时，通过配置it的第二个入参，为每个用例添加过滤参数。此参数用于为测试用例添加标注，不添加则参数默认为0表示未被标注。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/2d/v3/noCpgYTRTIqN464iGf8HzQ/zh-cn_image_0000002778923075.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=D97EBD9BD85AB4808A761B0FB4B6E391ADDDF062DBDCB6A266378F8DA9909892)

2. 打开**运行/调试配置**窗口，在**Test Args**输入框中添加测试参数。例如将测试参数配置为level=1; size=medium。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d3/v3/I5vhZF2hRhCvo75zeBUW9w/zh-cn_image_0000002779082935.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=7982C85BCB1A0FEBE92FC5E984CC317531175B885C6A932DA77E59B5AB584A62)


| Key | 含义说明 | Value取值范围 |

| --- | --- | --- |

| level | 用例级别 | "0","1","2","3","4", 例如：-s level 1 |

| size | 用例粒度 | "small","medium","large", 例如：-s size small |

| testType | 用例测试类型 | "function","performance","power","reliability","security","global","compatibility","user","standard","safety","resilience", 例如：-s testType function |
3. 完成以上配置后，在运行此项配置对应的测试任务时，只运行过滤后的测试用例。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/67/v3/ygOuQ-R_RweqJay5RW3Z7Q/zh-cn_image_0000002749483858.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=649C54684C28B1208C0CB950398E9F93D3938AE6DD3E014F9F97A49BE91D7330)

 
 

### 设置调试代码类型

打开**测试配置**窗口，点击**调试器**页签，设置调试类型。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/b/v3/QuA_jMTNSEmwhCsPPEXY5w/zh-cn_image_0000002749323994.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=756BAE97EA25726A6DDA75F3420678588E3940AFC34ABD079C2F2C3720671A2D)

 
调试类型默认为Detect Automatically，关于各调试类型的说明如下表所示：
  

| 调试类型 | 调试代码 |
| --- | --- |
| Detect Automatically | 新建工程默认调试器选项。根据工程模块及其依赖的模块涉及的编程语言，自动启动对应的调试器。 |
| ArkTS/JS | 调试ArkTS代码调试JS代码 |
| Native | 仅调试C/C++代码 |
| Dual(ArkTS/JS + Native) | 调试C/C++工程的ArkTS/JS和C/C++代码 |
 
 
> [!NOTE]
> 调试C++代码时，当前模块及所有依赖的HSP模块的 Address Sanitizer配置 要保持一致，若不一致，可能无法进入C++代码的断点处。

 
 

### ASan检测

Instrument Test针对C/C++方法提供ASan检测能力，关于ASan的介绍请参考[ASan检测](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-asan)，当前不支持JS语言。
 1. 在运行/调试配置窗口，选择对应的Instrument Test，点击**诊断**页签，勾选**Address Sanitizer**选项，勾选后，测试包和源码包均开启ASan能力。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/6a/v3/d0z89mLPSy2vfu_Kq6nqVQ/zh-cn_image_0000002749324002.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=A7FFBB63C6EA64E5FE842B7DA681CDF0005AAFE3AA4F049E94E9B3561A220B5B)

2. 如果有引用本地library，需在library模块的build-profile.json5文件中，配置arguments字段值为“-DOHOS_ENABLE_ASAN=ON”，表示以ASan模式编译so文件。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/8/v3/VLC76W0JRmqQBgu20RmPfg/zh-cn_image_0000002778923085.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=2303AFC01E6E9C371C819A788331F35EEC8A20342FE10740381B0BBBAC377420)

3. 运行测试用例。
4. 当程序出现内存错误时，弹出ASan log信息，点击信息中的链接即可跳转至引起内存错误的代码处。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/f6/v3/OnLVJ66xQDWl2bFvzj1vEg/zh-cn_image_0000002749483882.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=62F0F54A74C0493799D6EEE52B813CE9AC93B6CA874783C61DE5980ED2CCEC16)
