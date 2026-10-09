# Hot Reload

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-hot-reload

鸿蒙电脑DevEco Studio提供Hot Reload（热重载）能力，支持开发者在真机或多设备预览器上运行/调试应用时，修改代码并保存后无需重启应用，在真机或预览器上即可使用最新的代码，帮助开发者更快速地进行调试。
 
针对大多数代码修改场景，热重载均能提供支持，但是一些特殊场景需要通过热重载+重启应用后方可生效，因此，DevEco Studio提供基于热重载的增强能力——热重启。开启热重启开关后，DevEco Studio在遇到热重载不支持的场景时，将自动切换至热重启以获取更强的支持能力。
 
热重载和热重启均不支持C++文件和资源文件的修改，针对该问题，DevEco Studio提供基于热重启的增强能力——冷重载。开启冷重载开关后，并且设备版本在API 24及以上，DevEco Studio在增量调试C++代码及资源文件时，会自动切换至冷重载。
 
> [!NOTE]
> Hot Reload不支持卡片，不建议在hotReload模式下执行与卡片相关的操作。

 

## 热重载、热重启、完全重启的区别

- **热重载**：不重启应用，可保留应用状态，但整个过程会重新运行入口文件内的逻辑。
- **热重启**：在运行流程上，与热重载相比，主要区别在于会重启应用，不保留应用状态，支持更广泛的ArkTs代码修改快速生效。一旦执行了热重启，后续热重载流程均会被热重启取代。
- **完全重启**：会完全重新运行应用，该任务较为耗时，因为它会重新全量编译代码和资源文件。

 
 

## 使用约束
 

| 修改文件 | 热重载 | 热重启 | 说明 |
| --- | --- | --- | --- |
| 修改Entry入口模块内ets、ts代码文件 | 支持 | 支持 | - |
| 修改Entry直接或间接依赖的Har模块内代码文件 | 支持 | 支持 | Har模块与Entry模块间无Hsp |
| 修改Entry直接或间接依赖的Hsp模块内代码文件 | 不支持 | 不支持 | - |
| 引入的其他工程Har模块内代码文件 | 支持 | 支持 | Har模块与Entry模块间无Hsp |
| 引入的其他工程Hsp模块内代码文件 | 不支持 | 不支持 | - |
| 修改worker线程文件 | 不支持 | 不支持 | - |
| 修改模块目录下Index文件 | 支持 | 支持 | - |
| 启动应用后新增的代码文件 | 不支持 | 不支持 | - |
| C++、so文件 | 不支持 | 不支持 | - |
| resource资源文件（如修改string.json文件的内容） | 不支持 | 不支持 | 支持对资源引用的修改，例如把\$r('app.color.greenColor')改成\$r('app.color.redColor') |
 
  

| 代码元素 | 变更行为 | 热重载 | 热重启 | 说明 |
| --- | --- | --- | --- | --- |
| UI代码(如修改字号、颜色等) | 新增、修改、删除 | 支持 | 支持 | - |
| UI相应事件(如添加onClick事件等) | 新增、修改、删除 | 支持 | 支持 | - |
| import | 新增 | 部分支持 | 部分支持 | 不支持从启动应用时未加载的文件中import模块。 |
| import | 修改、删除 | 支持 | 支持 | - |
| 动态import lazy import napi_load_module napi_load_module_with_info | 新增 | 部分支持 | 部分支持 | 不支持从启动应用时未加载的文件中import模块。 |
| 动态import lazy import napi_load_module napi_load_module_with_info | 修改、删除 | 支持 | 支持 | - |
| export | 新增 | 部分支持 | 部分支持 | 新增export default语句时应同步在调用文件内新增对应import语句，否则将失败。 |
| export | 修改、删除 | 支持 | 支持 | - |
| 装饰器(@State、@Prop等) | 新增、修改、删除 | 部分支持 | 部分支持 | 热重载、热重启：@Entry修饰的文件支持@Styles新增、修改、删除 热重启：@Entry修饰的文件支持@State新增、修改和删除 |
| declare声明变量 | 新增、修改、删除 | 支持 | 支持 | - |
| Struct代码块 | 新增 | 部分支持 | 支持 | @Entry修饰的文件内不支持新增Struct代码块热重载，其他文件支持。 |
| Struct代码块 | 修改 | 部分支持 | 支持 | @Entry修饰的文件不支持成员变量、成员函数热重载，其他文件支持。 |
| Struct代码块 | 删除 | 支持 | 支持 | - |
| 类 | 新增 | 部分支持 | 支持 | @Entry修饰的文件内不支持新增包含成员函数的class，其他文件支持。 |
| 类 | 修改 | 部分支持 | 支持 | @Entry修饰的文件内class不支持新增成员函数，其他文件支持。 |
| 类 | 继承 | 部分支持 | 支持 | @Entry修饰的文件内不支持类继承及被继承场景，其他文件支持。 |
| 类 | 删除 | 支持 | 支持 | - |
| 接口 | 新增、删除 | 支持 | 支持 | - |
| 接口 | 修改 | 部分支持 | 支持 | @Entry修饰的文件内不支持接口对象修改，其他文件支持。 |
| 枚举 | 新增、修改 | 部分支持 | 支持 | @Entry修饰的文件内不支持新增枚举，不支持修改枚举的键和值，其他文件支持。 |
| 枚举 | 删除 | 支持 | 支持 | - |
| 匿名函数 | 新增、修改、删除 | 支持 | 支持 | - |
| Lambda函数 | 新增、修改、删除 | 支持 | 支持 | - |
| 闭包函数 | 新增、修改、删除 | 支持 | 支持 | - |
| 闭包变量 | 新增、删除 | 部分支持 | 部分支持 | 热重载仅支持顶层闭包变量（不包括this变量）的新增或删除。 热重启不支持首次新增this变量或删除所有this变量。 |
| 闭包变量 | 修改 | 部分支持 | 支持 | 热重载不支持顶层闭包变量的修改 |
| 自定义组件 | 新增、修改、删除 | 部分支持 | 支持 | 热重载：@Entry修饰的文件内仅支持通过import方式引入的自定义组件的新增和修改。 |
 
  

| 场景 | 热重载 | 热重启 | 说明 |
| --- | --- | --- | --- |
| 命中断点时 | 不支持 | 不支持 | 点击Resume Program继续执行后再进行热重载/热重启 |
| 修改跳转的其他ability页面 | 不支持 | 支持 | 修改代码并执行热重载后，重新拉起该ability页面可生效 |
 
 
 

## 开启热重启/冷重载（可选）

如果需要使用热重启或冷重载的能力，先打开对应开关：点击菜单栏点击**文件 > 设置 > 扩展 > 热重载**，勾选以下选项。
 
- **启用热重启**：热加载并重启应用。
- **启用冷重载**：增量构建并重启应用。

 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ad/v3/jx-24vFHRoKLoh_oFOg6pg/zh-cn_image_0000002749483788.png?HW-CC-KV=V1&HW-CC-Date=20261009T012528Z&HW-CC-Expire=86400&HW-CC-Sign=FA856F12CF36E816D1CB809B911A19B26B65EB006D10F7CBEE5DE4035D18ED06)

 
 

## 操作步骤
1. 连接真机设备或多设备预览器。
2. 在下拉菜单中，将运行/调试配置切换为**Hot Reload**的配置
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/17/v3/smNB_jOrTpyLSlOORwLqhQ/zh-cn_image_0000002749483792.png?HW-CC-KV=V1&HW-CC-Date=20261009T012528Z&HW-CC-Expire=86400&HW-CC-Sign=0CADD7BB5A321B30A60FD1BA2DEEA31C84C236DF3A7529070EEDD08DF14CC49C)
。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/c/v3/CCGnFbZWRSmZkZ1_q3yQzA/zh-cn_image_0000002779082851.png?HW-CC-KV=V1&HW-CC-Date=20261009T012528Z&HW-CC-Expire=86400&HW-CC-Sign=2439E3E2FC97A12F2D7C8E0FE90EBB81777D1F273DF6BB0F9A3DFD14B4BFA342)

3. 运行/调试应用，请参考[使用本地真机运行应用/元服务](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-run-device)或[使用多设备预览器运行应用/元服务](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-run-previewer)。
4. 修改代码后，可以通过如下操作，查看设备上修改后的显示效果。
方式一：点击热重载![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/06/v3/fMXWdzbXRquBuQyYld0Ilg/zh-cn_image_0000002778923005.png?HW-CC-KV=V1&HW-CC-Date=20261009T012528Z&HW-CC-Expire=86400&HW-CC-Sign=60CA7B2505144CDF8E0FCC816C0CB2789FD13A72D1D0A7635A61484EB474B59B)按钮：
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/8f/v3/SCZbXgA9TgqcTcD-ViJVsg/zh-cn_image_0000002778923007.png?HW-CC-KV=V1&HW-CC-Date=20261009T012528Z&HW-CC-Expire=86400&HW-CC-Sign=7BA3C84C93740A6585F5875903BE475B59C20B5A555444B722F8B2F9E490DDE9)

5. 方式二：通过快捷键方式触发热重载：需要先在菜单栏点击**文件 > 设置 > 扩展 > 热重载**，勾选**保存时执行热重载**。修改代码后通过快捷键**Ctrl + S**或**失焦**即可触发热重载。方式二不支持冷重载，如需使用冷重载功能，请使用方式一。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d0/v3/xAYEeyNrSN6CfN4E1xbQ5A/zh-cn_image_0000002749323922.png?HW-CC-KV=V1&HW-CC-Date=20261009T012528Z&HW-CC-Expire=86400&HW-CC-Sign=A23CEF78124A879B7DEAE4EEBADC4EEF769148698F6F6D60C6068200D9230681)

6. 点击停止按钮终止运行/调试运行，退出Hot Reload模式。
