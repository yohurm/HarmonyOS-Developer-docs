# debug启动调试

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-debug-arkts-debug

可以按照如下方式启动调试会话。
 1. 如果需要设置断点调试，找到需要暂停的代码片段，点击该代码行的左侧边线，或将光标置于该行上并按Ctrl + F8（macOS为Command+F8）。如果无法添加断点，请查看FAQ[调试过程中无法添加断点](https://developer.huawei.com/consumer/cn/doc/harmonyos-faqs/faqs-app-debugging-1)。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/57/v3/kmQvHyVYTkCh2D-emzQMTA/zh-cn_image_0000002701822706.png?HW-CC-KV=V1&HW-CC-Date=20261009T012803Z&HW-CC-Expire=86400&HW-CC-Sign=292D5C55787A1AA6F5DAF2B8E61167D9189153DEF638F785E8500BADB6394956)


  设置断点后，调试能够在正确的断点处中断，并高亮显示该行。
2. 在设备选择框中，选择调试的设备。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/22/v3/pFvrjRuqS96RbrPG6pIEDQ/zh-cn_image_0000002701662782.png?HW-CC-KV=V1&HW-CC-Date=20261009T012803Z&HW-CC-Expire=86400&HW-CC-Sign=0AFE56729ADFDD9F9AB61E57C217CC2CAEE492B17163BF269D098B1A2A5C72C1)

3. 选择启动调试的配置，在模块选择框中选择需要调试的模块。也可以通过Edit Configurations[配置调试参数](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-run-debug-configurations)。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/e6/v3/2TGzzSzIQuePtUnBn26g7g/zh-cn_image_0000002731541975.png?HW-CC-KV=V1&HW-CC-Date=20261009T012803Z&HW-CC-Expire=86400&HW-CC-Sign=CC17AF4B8CE3625489D79C2CB198126CDEC1251A7B984CC48F5E8FBAA766D7AF)

4. 在工具栏中，单击Debug![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/df/v3/G__UyhwcS169JxEtblI1qw/zh-cn_image_0000002731382003.png?HW-CC-KV=V1&HW-CC-Date=20261009T012803Z&HW-CC-Expire=86400&HW-CC-Sign=14F24EAAB4F7463B9E0CE4D90CB5E6FF5202D745FD8CC172291925836FD170BA)。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/69/v3/4u5NRRMVQPu5E3equhbgrg/zh-cn_image_0000002731382007.png?HW-CC-KV=V1&HW-CC-Date=20261009T012803Z&HW-CC-Expire=86400&HW-CC-Sign=D32AF52D7BBBAD5D1A5C6B478C879DC1DFD88D3D7B66735CBB715C6F1906033A)


  或者在工具栏中Run中选择Debug。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/c8/v3/3H3M2qwXRciSXMRAzJ9YWA/zh-cn_image_0000002731541981.png?HW-CC-KV=V1&HW-CC-Date=20261009T012803Z&HW-CC-Expire=86400&HW-CC-Sign=9C5367CC05F40539964F6338660F7DA0F9959463ED1709FCF8AD85B29FB2C002)

5. 启动调试后，开发者可以通过[调试器](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-debug-arkts-debugger)进行代码调试。

  如有断点会在断点处高亮，并展示当前断点处的Frames和Variables。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ef/v3/fwYief29SfyqtiOu7VFRLA/zh-cn_image_0000002701822704.png?HW-CC-KV=V1&HW-CC-Date=20261009T012803Z&HW-CC-Expire=86400&HW-CC-Sign=8FE87F2CD09C0FF59D3A6EB0C36DAAAE64CA6B46B502F2FFC62EDD6DBC5D96CA)
