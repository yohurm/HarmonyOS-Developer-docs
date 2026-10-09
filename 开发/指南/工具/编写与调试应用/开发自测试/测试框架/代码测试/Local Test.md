# 本地测试（Local Test）

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-local-test

> [!NOTE]
> 当前不支持测试C/C++方法及系统API。

 

## 创建Local Test测试用例
1. 在工程目录下打开待测试模块（支持HAP、HAR、HSP模块）下的ets文件，将光标置于代码中任意位置，单击**右键 > Show Context Actions > Create Local Test**或快捷键**Alt+Enter（macOS为Option+Enter） > Create Local Test**创建测试类。

  
![](assets/Local%20Test/file-20260514133037800-1.png)

2. 在弹出的Create Local Test窗口，输入或选择如下参数。

  
- **Testing library**：测试类型，默认为DECC-ArkTSUnit。

3. **ArkTS name**：创建的测试文件名称，测试文件中包含了测试用例。测试文件名称要求在工程目录范围内具有唯一性，仅支持字母、数字、下划线（_）和点（.）。

4. **Destination package**：测试文件存放的位置，建议存放在待测试模块的test目录下。

5. DevEco Studio在test目录下自动生成对应的测试类。在测试类中，DevEco Studio会生成对应方法的用例模板，具体测试代码需要开发者根据业务逻辑进行开发，具体请参考[单元测试框架](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/unittest-guidelines)。

  
> [!NOTE]
> 您也可以手动在test文件夹下创建测试用例，手动创建后，需要在List.test.ets文件中添加创建的用例类。


  

  ## 运行Local Test测试用例

  

  ### 运行模式

  可以采用运行工程目录（test）、测试文件（如Index.test.ets）、测试套件（describe）、测试方法（it）的方式来执行Local Test，各级别测试执行入口如下。

| ![](assets/Local Test/file-20260514133037800-12.png) | ![](assets/Local Test/file-20260514133037800-13.png) |

| --- | --- |

| 目录级 | 文件级 |

| ![](assets/Local Test/file-20260514133037800-14.png) | ![](assets/Local Test/file-20260514133037800-15.png) |

| 套件级 | 方法级 |

  以文件级别为例，在工程目录中，选中文件，单击**右键 > Run'测试文件名称'**，执行测试。

  
![](assets/Local%20Test/file-20260514133037800-16.png)


  也可以通过如下方式，执行Local Test：
在工具栏主菜单单击**Run > Run'测试名称'**。
- 在DevEco Studio的右上角，选择一项测试任务的配置，然后单击右侧的![icon](assets/Local%20Test/file-20260514133037800-17.png)按钮，执行Local Test。
![](assets/Local%20Test/file-20260514133037800-2.png)


 
 
执行完测试任务后，查看测试结果。
 

![](assets/Local%20Test/file-20260514133037800-3.png)

 
 

### 调试模式

调试模式相比运行模式增加了断点管理功能。在断点命中时，可以选择单步执行、步入步出、进入下个断点等方式进行调试，另外可以使用线程堆栈可视化、变量和表达式可视化功能，快速定位问题。
 
以文件级别为例，在添加断点之后，在工程目录中，选中文件，单击**右键 > Debug'测试文件名称'**，以调试模式执行测试任务。
 

![](assets/Local%20Test/file-20260514133037800-4.png)

 
在断点命中时，下方将出现Debug窗口。开发者可在该窗口中进行断点管理与基础调试能力的可视化操作，在断点命中时可查看当前线程的变量和堆栈信息。
 

![](assets/Local%20Test/file-20260514133037800-5.png)

 
 

断点命中时，在代码编辑器窗口单击右键，在弹出的菜单中将出现调试模式特有功能，如计算表达式、添加变量监视等。
 

![](assets/Local%20Test/file-20260514133037800-6.png)

 
在跳出所有断点后，测试结束，与运行模式相同，在测试窗口查看测试结果。
 

![](assets/Local%20Test/file-20260514133037800-7.png)

 
 

### 覆盖率统计模式

在LocalTest运行的基础上支持代码覆盖率统计，当前仅支持ArkTS工程。
 
开发者可以自定义参与覆盖率测试的本地文件或远程源码har包，具体配置方法请参考[配置覆盖率过滤文件](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-ui-test#section13756446154)。
 
如前所述，覆盖率统计模式也有多级别入口，以文件级别为例，有两种方式启动测试：
 
- 方式一：在工程目录中，选中文件，单击**右键 > Run '测试文件名称' with Coverage**，以覆盖率统计模式执行测试任务。
![](assets/Local%20Test/file-20260514133037800-8.png)


 
 

- 方式二：在DevEco Studio的右上角，选择测试任务，然后单击右侧的![icon](assets/Local%20Test/file-20260514133037800-9.png)按钮，执行测试。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/6a/v3/WnIGbmSpQb6r62XZBYg5dA/zh-cn_image_0000002731383045.png?HW-CC-KV=V1&HW-CC-Date=20261009T012816Z&HW-CC-Expire=86400&HW-CC-Sign=9D75E514CD4EAFEBF543744C2420BD083840D45F86BDDD34F4DA206DF6D22B19)


 
启动测试后，进行编译构建，底部将出现Cover窗口，构建结束后自动拉起Cover窗口，测试任务结束后，窗口中会打印测试报告的路径。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d9/v3/FHswGnMQTBGGlWJkdk8M_Q/zh-cn_image_0000002731543003.png?HW-CC-KV=V1&HW-CC-Date=20261009T012816Z&HW-CC-Expire=86400&HW-CC-Sign=2BEE507EAD2813408E0CBF46DDDD2BBC42773BACE6E1C3770C7E43614BEF328D)

 
 

点击链接可打开报告，查看代码覆盖率详情，关于覆盖率的计算方式请参考[查看覆盖率报告](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-ui-test#section10394362109)。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/85/v3/7tRZ_RMvR7-mq6uSgnCrag/zh-cn_image_0000002731543007.png?HW-CC-KV=V1&HW-CC-Date=20261009T012816Z&HW-CC-Expire=86400&HW-CC-Sign=F7F908616625A9060F4FFA97C92B9019BE3EAB48A8984CD887BEFF242F32165A)

 
在Cover窗口中，单击rerun按钮可以按照之前的设置，重新执行覆盖率用例。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/f6/v3/Q-Oa0iDnTTudyzPW8HpQzw/zh-cn_image_0000002701823752.png?HW-CC-KV=V1&HW-CC-Date=20261009T012816Z&HW-CC-Expire=86400&HW-CC-Sign=AE00CE727DD466C7BFBDA6B84A5282B86655E1F256599C73190C5EAB72629B72)

 
 

## （可选）自定义测试用例运行任务

默认情况下，测试用例可直接运行。如果需要自定义测试用例运行任务，可通过如下方法进行设置。
 1. 在工具栏主菜单单击**Run**>**Edit Configurations**，进入Run/Debug Configurations界面。
2. 在**Run/Debug Configurations**界面，单击**+**按钮，在弹出的下拉菜单中，单击**Local Test**。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/94/v3/oFjQfpo0SXqyyHUWY4VvEw/zh-cn_image_0000002701663802.png?HW-CC-KV=V1&HW-CC-Date=20261009T012816Z&HW-CC-Expire=86400&HW-CC-Sign=50E7CE962DCFAA8C7FFB4F3387C652D099CDCA6DA33F0EF2C92B1EC8358ECD6C)

3. 根据实际情况，配置Local Test的运行参数。 然后单击**OK**，完成配置。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ad/v3/zvSx-ArcRAuKRYaO8-pEdg/zh-cn_image_0000002701823734.png?HW-CC-KV=V1&HW-CC-Date=20261009T012816Z&HW-CC-Expire=86400&HW-CC-Sign=7D430C099B49B5DFE08FF5752E6CF9BAEE7F60B6C8988669F92DC56B0BE2DD5D)

 
 

## 使用命令行执行测试

通过命令行方式执行Local Test，在工程根目录下执行命令：
```bash
hvigorw test -p module={moduleName} -p coverage={true | false} -p scope={suiteName}#{methodName} -p patch={patchPath}
```
 
- module：执行测试的模块。缺省默认是执行所有模块的用例。
- coverage：是否生成覆盖率报告，缺省默认是true，在<module-path>/.test/default/outputs/test/reports路径下生成两份报告，一份是html格式（index.html），一份是json格式（coverageReport.json），具体参考[查看覆盖率报告](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-ui-test#section10394362109)。
- scope：格式为{suiteName}#{methodName}或{suiteName}，分别表示测试用例级别或测试套件级别的测试，缺省默认是执行当前模块的所有用例。
- patch：可选参数，指定代码补丁文件路径，用于统计增量代码覆盖率。仅支持绝对路径，后缀必须为.patch或.diff，可以通过git diff等命令生成。从26.0.0版本开始支持。

 
> [!NOTE]
> 多个module和scope之间用英文逗号隔开。 暂不支持在Linux上执行该命令。

 
 
测试结果文件：<module-path>/.test/default/intermediates/test/coverage_data/test_result.txt
