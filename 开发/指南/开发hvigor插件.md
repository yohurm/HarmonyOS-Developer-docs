# 开发hvigor插件

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-hvigor-plugin

Hvigor允许开发者实现自己的插件，开发者可以定义自己的构建逻辑，并与他人共享。
 
Hvigor主要提供了两种方式来实现插件：基于hvigorfile脚本开发插件、基于typescript项目开发。
 
关于插件开发的具体实践请参考[定制hvigor插件开发实践](https://developer.huawei.com/consumer/cn/doc/best-practices/bpta-custom-hvigor-plugin)。
 

## 基于hvigorfile脚本开发

基于hvigorfile.ts脚本开发的方式，其优点是可实现快速开发，直接编辑工程或模块下hvigorfile.ts即可编写插件代码，不足之处是在多个项目中，无法方便地进行插件代码的复用和共享分发。
 
在构建脚本中编写代码时，支持代码补全、代码生成、代码重构等代码编辑能力，具体使用方式请参考[代码阅读](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-editer-overview)、[代码生成/补全](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-code-completion)、[代码重构](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-next-code-refactoring)。
 
若开发者需要创建新的构建脚本，推荐将这些脚本统一放在工程或模块的scripts目录下，以便与应用代码进行隔离，示例如下。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/3/v3/Ama4n6U4S5ei3Ix0ERMt2g/zh-cn_image_0000002749483560.png?HW-CC-KV=V1&HW-CC-Date=20261009T012532Z&HW-CC-Expire=86400&HW-CC-Sign=F0F61EB876973D28CEB9AA51169F81A5EEC28F3B171709A6FD39C7D1A1DF2B8B)

 
以工程级hvigorfile.ts脚本为例，开发步骤如下。
 1. 导入模块依赖，更多接口请参考[扩展构建API](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-hvigor-apis)。

  
```text
// 工程级hvigorfile.ts
import { appTasks } from '@ohos/hvigor-ohos-plugin';
import { HvigorPlugin, HvigorNode } from '@ohos/hvigor';
```

2. 编写插件代码，实现HvigorPlugin接口。

  
```text
<span style="color: rgb(128,128,128);">// 工程级</span>hvigorfile.ts
function <span style="color: rgb(0,0,255);">customPlugin</span><span style="color: rgb(0,0,255);">()</span><span style="color: rgb(181,106,1);">: </span><span style="color: rgb(0,0,255);">HvigorPlugin </span><span style="color: rgb(255,0,170);">{</span>
  return <span style="color: rgb(255,0,170);">{</span>
    <span style="color: rgb(0,0,255);">pluginId</span><span style="color: rgb(181,106,1);">: </span><span style="color: rgb(255,0,170);">'customPlugin'</span><span style="color: rgb(181,106,1);">,</span>
    <span style="color: rgb(0,0,255);">apply</span><span style="color: rgb(0,0,255);">(</span><span style="color: rgb(0,0,255);">node</span><span style="color: rgb(181,106,1);">: </span><span style="color: rgb(0,0,255);">HvigorNode</span><span style="color: rgb(0,0,255);">) </span><span style="color: rgb(255,0,170);">{</span>
      <span style="color: rgb(128,128,128);">// </span><span style="color: rgb(128,128,128);">插件主体</span>
      <span style="color: rgb(0,0,255);">console</span><span style="color: rgb(181,106,1);">.</span><span style="color: rgb(0,0,255);">log</span><span style="color: rgb(0,0,255);">(</span><span style="color: rgb(255,0,170);">'hello customPlugin!'</span><span style="color: rgb(0,0,255);">)</span><span style="color: rgb(181,106,1);">;</span>
    <span style="color: rgb(255,0,170);">}</span>
<span style="color: rgb(255,0,170);">  }</span>
<span style="color: rgb(255,0,170);">}</span>
```

3. 在导出声明中使用插件。

  
```text
// 工程级hvigorfile.ts
export default <span style="color: rgb(255,0,170);">{</span>
  <span style="color: rgb(0,0,255);">system</span><span style="color: rgb(181,106,1);">: </span><span style="color: rgb(0,0,255);">appTasks</span><span style="color: rgb(181,106,1);">,</span>
  <span style="color: rgb(0,0,255);">plugins</span><span style="color: rgb(181,106,1);">:</span><span style="color: rgb(0,0,255);">[</span>
    <span style="color: rgb(0,0,255);">customPlugin</span><span style="color: rgb(0,0,255);">()  </span><span style="color: rgb(128,128,128);">// </span><span style="color: rgb(128,128,128);">应用自定义</span><span style="color: rgb(128,128,128);">Plugin</span>
  <span style="color: rgb(0,0,255);">]</span>
<span style="color: rgb(255,0,170);">}</span>
```

4. 执行Hvigor命令。

  执行Hvigor命令时，在Hvigor生命周期配置阶段执行插件中的apply方法。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/0/v3/OLvYt-XmTTCTrv5rOM5pPw/zh-cn_image_0000002778922769.png?HW-CC-KV=V1&HW-CC-Date=20261009T012532Z&HW-CC-Expire=86400&HW-CC-Sign=6CC1A29106705EE6516D2D6265D0D7A9E9B329CB6FF6F25C767EF60E132974C4)

 
 

## 基于typescript项目开发

基于typescript项目开发的方式，能够较好地弥补上一小节中使用hvigorfile脚本编写插件代码不易复用和共享分发的问题，因此通常情况下推荐此方式开发。
 
 

### 初始化typescript项目
1. 创建一个空目录。

  在命令行工具中使用cd命令进入空目录下。
2. 安装typescript模块。

  
```bash
// 全局安装TypeScript
npm install typescript -g
```

3. 初始化npm项目。

  执行如下命令，根据命令行指示配置项目。初始化完成后会生成package.json文件。
```bash
// 初始化一个npm项目
npm init
```

4. 生成typescript配置文件。

  执行如下命令生成tsconfig.json文件。
```bash
// 初始化typeScript配置文件
tsc --init
```


  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a3/v3/suD-5y8ARIOjxDsWEBHDwg/zh-cn_image_0000002749323686.png?HW-CC-KV=V1&HW-CC-Date=20261009T012532Z&HW-CC-Expire=86400&HW-CC-Sign=BCAB1CCE80DF3D7843CB31AB29FC7D849EDF929F7C1BD766BCFA04B16E9E56CF)

5. 删除verbatimModuleSyntax字段。

  检查tsconfig.json文件是否存在verbatimModuleSyntax字段，如果存在且配置为true，会导致无法使用ESM语法，编译时会报错，因此需要删除该字段。
 
 

### 开发插件
1. 配置npm镜像仓库地址，用于安装@ohos/hvigor插件。

  在工程目录下创建.npmrc文件，配置如下信息：

  
```text
registry=https://repo.huaweicloud.com/repository/npm/
@ohos:registry=https://repo.harmonyos.com/npm/
```

2. 添加依赖声明。

  打开package.json添加devDependencies配置。

  
```json
"devDependencies": {
    "@ohos/hvigor": "6.26.2"
}
```
 
> [!NOTE]
> 如果依赖配置在dependencies中，会导致使用插件时编译报错。

3. 安装依赖。

  执行如下命令安装依赖。
```bash
npm install
```

4. 编写插件代码。

  在src/plugin目录下创建custom-plugin.ts文件，编写插件代码，更多接口请参考[扩展构建API](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-hvigor-apis)。

  
```text
import type <span style="color: rgb(255,0,170);">{ </span><span style="color: rgb(0,0,255);">HvigorNode</span><span style="color: rgb(181,106,1);">, </span><span style="color: rgb(0,0,255);">HvigorPlugin </span><span style="color: rgb(255,0,170);">} </span>from <span style="color: rgb(255,0,170);">'@ohos/hvigor'</span><span style="color: rgb(181,106,1);">;</span>

export function <span style="color: rgb(0,0,255);">customPlugin</span><span style="color: rgb(0,0,255);">()</span><span style="color: rgb(181,106,1);">: </span><span style="color: rgb(0,0,255);">HvigorPlugin </span><span style="color: rgb(255,0,170);">{</span>
  return <span style="color: rgb(255,0,170);">{</span>
    <span style="color: rgb(0,0,255);">pluginId</span><span style="color: rgb(181,106,1);">: </span><span style="color: rgb(255,0,170);">'customPlugin'</span><span style="color: rgb(181,106,1);">,</span>
    <span style="color: rgb(0,0,255);">apply</span><span style="color: rgb(0,0,255);">(</span><span style="color: rgb(0,0,255);">node</span><span style="color: rgb(181,106,1);">: </span><span style="color: rgb(0,0,255);">HvigorNode</span><span style="color: rgb(0,0,255);">) </span><span style="color: rgb(255,0,170);">{</span>
      <span style="color: rgb(0,0,255);">console</span><span style="color: rgb(181,106,1);">.</span><span style="color: rgb(0,0,255);">log</span><span style="color: rgb(0,0,255);">(</span><span style="color: rgb(255,0,170);">'hello customPlugin!'</span><span style="color: rgb(0,0,255);">)</span><span style="color: rgb(181,106,1);">;</span>
    <span style="color: rgb(255,0,170);">}</span>
<span style="color: rgb(255,0,170);">  }</span>
<span style="color: rgb(255,0,170);">}</span>
```

5. 导出插件。

  创建index.ts文件，并在该文件中声明插件方法的导出。由于.ts最终会编译成.js文件，因此需要导出.js文件。

  
```text
export { customPlugin } from './src/plugin/custom-plugin.js';
```

 
 

### 发布插件

typescript项目本质上是一种npm项目，插件发布流程遵循npm发布规范。详情请查询npm官方资料。
 
发布npm包流程：
 1. 配置registry。

  打开工程目录下的.npmrc文件，配置您需要发布的镜像仓库。

  
```text
registry=[npm镜像仓库地址]
```

2. 生成AccessToken。

  执行如下命令，注册并登录npm仓库，在工程目录下.npmrc文件中自动生成token信息。

  
```bash
npm login
```

3. 编译npm包。

  
```bash
tsc
```
 如果编译时报以下错误，请检查初始化项目时是否[删除了verbatimModuleSyntax](#li88369101451)。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/13/v3/R5pMQ-NYQiawj3d77Moz0Q/zh-cn_image_0000002779082623.png?HW-CC-KV=V1&HW-CC-Date=20261009T012532Z&HW-CC-Expire=86400&HW-CC-Sign=57118A7C330A41EA3372179D8AA3010A8FC346968C9F118C84711CDE1F21E0AA)

4. 发布npm包。

  执行如下命令，将npm项目打包并发布至镜像仓库。

  
```bash
npm publish
```

 
 

### 使用插件
1. 添加依赖。

  在工程下hvigor/hvigor-config.json5中添加自定义插件依赖，依赖项支持离线插件配置。

  
```json
<span style="color: rgb(255,0,170);">"dependencies"</span><span style="color: rgb(181,106,1);">: </span><span style="color: rgb(255,0,170);">{</span>
  <span style="color: rgb(255,0,170);">"custom-plugin"</span><span style="color: rgb(181,106,1);">: </span><span style="color: rgb(255,0,170);">"1.0.0"   </span><span style="color: rgb(128,128,128);">// </span><span style="color: rgb(128,128,128);">添加自定义插件依赖</span>
<span style="color: rgb(255,0,170);">}</span>
```

2. 安装依赖。

  
方式1：点击编辑器右上角**立即同步**或点击菜单**文件 -> 同步和刷新项目**进行同步后，鸿蒙电脑DevEco Studio将会根据hvigor-config.json5中的依赖配置自动安装。
3. 方式2：使用hvigorw命令行工具执行任一命令，命令行工具会自动执行安装构建依赖。
```bash
hvigorw --sync
```

4. 导入插件。

  根据插件编写时基于的node节点，确定导入的节点所在的hvigorfile.ts文件，在hvigorfile.ts中导入插件。

  
```text
import { customPlugin } from 'custom-plugin';
```

5. 使用插件。

  将自定义插件添加到export default的plugins中。

  
```text
export default <span style="color: rgb(255,0,170);">{</span>
  <span style="color: rgb(0,0,255);">system</span><span style="color: rgb(181,106,1);">: </span><span style="color: rgb(0,0,255);">appTasks</span><span style="color: rgb(181,106,1);">,</span>  // 以工程级hvigorfile.ts为例
  <span style="color: rgb(0,0,255);">plugins</span><span style="color: rgb(181,106,1);">:</span><span style="color: rgb(0,0,255);">[</span>
    <span style="color: rgb(0,0,255);">customPlugin</span><span style="color: rgb(0,0,255);">()  </span><span style="color: rgb(128,128,128);">// </span><span style="color: rgb(128,128,128);">应用自定义插件</span>
  <span style="color: rgb(0,0,255);">]</span>
<span style="color: rgb(255,0,170);">}</span>
```
