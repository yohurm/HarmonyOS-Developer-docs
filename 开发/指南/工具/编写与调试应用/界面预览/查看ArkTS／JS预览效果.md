# 查看ArkTS/JS预览效果

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-previewer-arkts-js

预览器支持ArkTS/JS应用/元服务“实时预览”和“动态预览”。
 
> [!WARNING]
> 预览支持Phone、Tablet、2in1、Car、Wearable、TV设备的ArkTS工程，支持LiteWearable和Wearable设备的JS工程。 预览器功能依赖于电脑显卡的OpenGL版本，OpenGL版本要求为3.2及以上。 预览时将不会运行Ability生命周期。 从DevEco Studio 6.0.0 Beta3版本开始，HAP/HSP引用HSP时支持预览，HAR模块引用HSP不支持预览，请直接在HSP内预览或为该HSP 设置Mock实现 。 预览场景下，不支持通过相对路径及绝对路径的方式访问resources目录下的文件。 预览不支持组件拖拽。 部分API不支持预览，如Ability、App、MultiMedia等模块。 Richtext、Web、Video、 XComponent 组件不支持预览。 不支持调用C++库的预览。 HAR在被应用/元服务使用时真机效果有区别，真机上实际效果应用不显示menubar，元服务显示menubar，但预览器都以不显示menubar为准。若开发HAR模块，请注意被元服务使用时预览器效果与真机效果的不同。

 
- **实时预览**：在开发界面UI代码过程中，如果添加或删除了UI组件，您只需**Ctrl+S**进行保存，然后预览器就会立即刷新预览结果。如果修改了组件的属性，则预览器会实时（亚秒级）刷新预览结果，达到极速预览的效果（当前版本极速预览仅支持ArkTS组件。支持部分数据绑定场景，如@State装饰的变量）。实时预览默认开启，如果不需要实时预览，请单击预览器右上角![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/8f/v3/G__amhiDRHy8losuma1WFQ/zh-cn_image_0000002731542297.png?HW-CC-KV=V1&HW-CC-Date=20261009T012822Z&HW-CC-Expire=86400&HW-CC-Sign=DE5672B8848261BD1ABD66E9609B2CF07F9525EEFA39A030B44001D4A5522385)按钮，关闭实时预览功能。
> [!NOTE]
> 开发者修改resources/base/profile目录下的配置文件（如main_pages.json/form_config.json），不支持触发实时预览，开发者需要点击重新加载 。


  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/e0/v3/Lg39pNPHQN-TCVpZhsGYlw/zh-cn_image_0000002701663102.gif?HW-CC-KV=V1&HW-CC-Date=20261009T012822Z&HW-CC-Expire=86400&HW-CC-Sign=F59FCE17B3CEBCBA9BAD519EF36A6A7ECB6ACECCAA4E3999F98EF8AEB8EDA762)

- **动态预览**：在预览器界面，可以在预览器中操作应用/元服务的界面交互动作，如单击、跳转、滑动等，与应用/元服务运行在真机设备上的界面交互体验一致。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/97/v3/TmeI87AtQF-2IGiaXo1ziA/zh-cn_image_0000002701823026.gif?HW-CC-KV=V1&HW-CC-Date=20261009T012822Z&HW-CC-Expire=86400&HW-CC-Sign=FF094521F0A85D2519958788D306B48235613F05F9EB43D9866DC143D1ABD2BE)


 
以ArkTS为例，使用预览器的方法如下：
 1. 创建或打开一个ArkTS应用/元服务工程。本示例以打开一个本地ArkTS Demo工程为例。
2. 在工程目录下，打开任意一个.ets文件（JS工程请打开.hml/.css/.js页面）。
3. 可以通过如下任意一种方式打开预览器，启动预览。

  
通过菜单栏，单击**View > Tool Windows > Previewer**打开预览器。
4. 在编辑窗口右上角的侧边工具栏，单击**Previewer**，打开预览器。
5. 点击按钮![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/47/v3/JKdE4Og6QKuv3CCjIrSJnw/zh-cn_image_0000002731382329.png?HW-CC-KV=V1&HW-CC-Date=20261009T012822Z&HW-CC-Expire=86400&HW-CC-Sign=0DB53763628FD43FC93B5CBB35764909C84A48B954DB1EFFA4DF7DDEED81AFA0)，停止预览。
