# 构建HAR

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-hvigor-build-har

构建模式：鸿蒙电脑DevEco Studio默认提供debug和release两种构建模式，同时支持开发者自定义构建模式。
 
产物格式：构建出的HAR包产物分为包含源码的HAR、包含js中间码的HAR以及包含字节码的HAR三种产物格式。
 
DevEco Studio默认构建字节码HAR，用于提升发布产物的安全性。
 

## 使用约束

HAR自身的构建不建议引用本地模块，可能导致其他模块依赖该HAR包时安装失败，如果安装失败，需要在工程级oh-package.json5中配置[overrides](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-oh-package-json5#zh-cn_topic_0000001792256137_overrides)。
 
 

## 创建模块
1. 新建工程，工程创建完成后，新建“Static Library”模块。模块创建方法可参考[添加模块](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-add-new-module)。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/dd/v3/SsPDQybURQShH5PT0oWGMg/zh-cn_image_0000002749323832.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=2B380B9A5EC5DF75A6AEF788BA9FA6D8D6B1E6841AC20B7722670A747B5D7D98)

2. 编写代码。

  
```ArkTS
library  // HAR根目录
  ├─libs  // 存放用户自定义引用的Native库，一般为.so文件
  └─src
  │   └─main
  │     ├─cpp
  │     │  ├─types  // 定义Native API对外暴露的接口  
  │     │  │  └─liblibrary  
  │     │  │      ├─index.d.ts
  │     │  │      └─oh-package.json5 
  │     │  ├─CMakeLists.txt  // CMake配置文件  
  │     │  └─napi_init.cpp  // C++源码文件
  │     └─ets  // ArkTS源码目录
  │     │  └─components
  │     │     └─MainPage.ets
  │     ├─resources  // 资源目录，用于存放资源文件，如图片、多媒体、字符串等  
  │     └─module.json5  // 模块配置文件，包含当前HAR的配置信息  
  ├─build-profile.json5  // Hvigor编译构建所需的配置文件，包含编译选项
  ├─hvigorfile.ts  // Hvigor构建脚本文件，包含构建当前模块的插件、自定义任务等
  ├─Index.ets  // HAR的入口文件，一般作为出口定义HAR对外提供的函数、组件等   
<strong>  └─</strong>oh-package.json5  // HAR的描述文件，定义HAR的基本信息、依赖项等
```

3. 在oh-package.json5中“main”字段定义导出文件入口。若不设置“main”字段，默认以当前目录下Index.ets为入口文件，依据.ets>.ts>.js的顺序依次检索。以将ets/components/MainPage.ets文件设置为入口文件为例：

  
```ArkTS
{
  <span style="color: rgb(102,14,122);">"main"</span>: <span style="color: rgb(0,128,0);">"./src/main/ets/components/MainPage.ets"</span>,
}
```

 
 

## 字节码HAR

默认产物是包含字节码的HAR包，其中包含abc字节码、资源文件、配置文件、readme、changelog声明文件、license证书文件，提升发布到ohpm中心仓产物的安全性。
 
字节码HAR包中包含的是编译后的abc字节码，当字节码HAR被其他应用模块(HAP/HSP)依赖时，执行应用模块的编译构建，不需要再对依赖的HAR进行语法检查和编译等操作，相比源码HAR，可以有效提升应用模块的编译构建效率，提高安全性，降低代码泄露的风险。
 
> [!NOTE]
> 由于构建字节码HAR需要生成二进制的格式，所以单独构建字节码HAR会比构建非字节码HAR耗时更多。

 
 

### 收益

- 字节码HAR可以降低代码泄露的风险，增加反编译获取代码逻辑的难度。

 
- 采用ArkTS/TS语言开发的字节码HAR，被HAP/HSP集成时，可以减少语法检查、转换的耗时，提高构建性能。
- 字节码HAR可以减少编译时node的进程占用，有效降低内存占用。
- 通过其他代码生成工具生成的js语言HAR包，编译构建成字节码HAR后，被HAP/HSP集成时，可以减少编译阶段处理的文件和代码数量，降低内存，提高构建性能。

 
 

### 使用场景

从功能上来说所有的源码HAR包都可以按照任意顺序切换成字节码HAR。但是由于字节码HAR编译和集成的特点，按照推荐场景或顺序来逐步切换字节码HAR可能会获得比较好的性能、内存收益。以下场景中推荐切换使用字节码HAR：
 
- 适用于SDK厂商对外提供SDK，以及高安全的场景，字节码HAR可以降低源码泄露的风险。
- 采用multi-repo的开发模式，在被主工程合并集成时，所有依赖的HAR均可以发布成字节码HAR，从而提高主HAP的构建效率。
- 采用mono-repo的开发模式，工程中含有单个代码文件较大，或通过代码生成工具生成的代码量较大的ArkTS/TS/JS 的二方、三方SDK(HAR包)时，可考虑将这些HAR包构建成字节码HAR。
- 对内存要求较高的场景，可以通过切换字节码HAR，降低内存的占用。
- 通过ArkTS/TS/JS编写的HAR，且在依赖链条中处于较为底层的叶子节点，含有较少的源码依赖时，切换为字节码HAR会有较好的收益。

 
 

### 约束条件

- 字节码HAR使用的依赖需要配置在本模块的oh-package.json5的dependencies或dynamicDependencies中，如果不配置，后续字节码HAR被集成时可能会出现运行时异常。如果出现异常，部分场景可通过在hvigor-config.json5中配置ohos.byteCodeHar.integratedOptimization后重新编译，具体请参考[编译行为差异说明](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-hvigor-dependencies#section957371853712)。
- 字节码HAR的oh-package.json5中配置的依赖名和依赖包的包名（即包内oh-package.json5中的name）需要保持一致。
- 依赖字节码HAR包时，该工程的build-profile.json5中的[useNormalizedOHMUrl](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-hvigor-build-profile-app#section13181758123312)必须设置为true。
- HAP/HSP/HAR依赖字节码HAR包时，HAP/HSP/HAR的oh-package.json5中配置的依赖名和字节码HAR包的oh-package.json5中的name需要保持一致。
- HAP/HSP/HAR代码中import使用字节码HAR包时，`import xxx from 'yyy'`的依赖名yyy要和本模块oh-package.json5中配置的依赖名保持一致（包括大小写）。
- 依赖字节码HAR包时，字节码HAR的compatibleSdkVersion不能大于工程的compatibleSdkVersion。

 
 

### 操作步骤
1. 将工程级build-profile.json5的useNormalizedOHMUrl设置为true。

  
> [!NOTE]
> 工程级build-profile.json5中useNormalizedOHMUrl字段默认为true，byteCodeHar缺省默认值为true。


  
```json
{
  <span style="color: rgb(102,14,122);">"app"</span>: {
    "products": [
      {
         "buildOption": {
           "strictMode": {
             "useNormalizedOHMUrl": true
           }
         }
      }
    ]
  }
}
```

2. 在HAR模块的build-profile.json5中，将byteCodeHar设置为true。

  
```json
{
  <span style="color: rgb(102,14,122);">"buildOption"</span>: {
    "arkOptions": {
      "byteCodeHar": true
    }
  }
}
```

3. 点击DevEco Studio界面上方![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/49/v3/e2PH_-kRTL2dWISBVtF2-g/zh-cn_image_0000002778922911.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=DFDCDA3CF3F9A04BBF43CCA5A60A6B8EBDE797C9320DF224975DD35A6920655B)右侧的![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/04/v3/JwC_pYd7SvK_8al0RnB9yA/zh-cn_image_0000002749483694.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=660E3F526EEBFBC6EEC4A57B8EBCFBC2E2A4608AADF5CC5B578B37A4B38E4F36)，选择**Product配置> 构建模式**。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ef/v3/KyPallpNRVWZwylFqKgLGw/zh-cn_image_0000002749323814.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=87E88E068E1E99762CA5BD56DA513036E54324B0CFF074D3B849679B930F907F)

4. （可选）在构建模式为release时，为保护代码资产，建议开启混淆，在模块级build-profile.json5文件的release的buildOptionSet配置中，将obfuscation/ruleOptions下的enable字段设置为true。混淆相关能力和具体规则请参考[混淆加固](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-build-obfuscation)。

  
```json
{
  <span style="color: rgb(135,16,148);">"apiType"</span>: <span style="color: rgb(6,125,23);">"stageMode"</span>,
  <span style="color: rgb(135,16,148);">"buildOption"</span>: {
  },
  <span style="color: rgb(135,16,148);">"buildOptionSet"</span>: [
    {
      <span style="color: rgb(135,16,148);">"name"</span>: <span style="color: rgb(6,125,23);">"release"</span>,
      <span style="color: rgb(135,16,148);">"arkOptions"</span>: {
        // 混淆相关参数
        <span style="color: rgb(135,16,148);">"obfuscation"</span>: {
          <span style="color: rgb(135,16,148);">"ruleOptions"</span>: {
            // true表示进行混淆，false表示不进行混淆。
            <span style="color: rgb(135,16,148);">"enable"</span>: <span style="color: rgb(0,51,179);">true</span>,
            // 混淆规则文件
            <span style="color: rgb(135,16,148);">"files"</span>: [
              <span style="color: rgb(6,125,23);">"./obfuscation-rules.txt"</span>
            ]
          },
          // consumerFiles中指定的混淆配置文件会在构建依赖这个library的工程或library时被应用
          <span style="color: rgb(135,16,148);">"consumerFiles"</span>: [
            <span style="color: rgb(6,125,23);">"./consumer-rules.txt"</span>
          ]
        }
      },
    },
  ],
  <span style="color: rgb(135,16,148);">"targets"</span>: [
    {
      <span style="color: rgb(135,16,148);">"name"</span>: <span style="color: rgb(6,125,23);">"default"</span>
    }
  ]
}
```

5. （可选）如果开发者希望自定义打包到HAR产物中的文件，可在HAR模块的build-profile.json5文件中，配置include或exclude字段，支持glob语法。

  
```json
<span style="color: rgb(135,16,148);">"buildOption"</span>: {
  <span style="color: rgb(135,16,148);">"packingOptions"</span>: {
    <span style="color: rgb(135,16,148);">"asset"</span>: {
      <span style="color: rgb(135,16,148);">"include"</span>: [<span style="color: rgb(6,125,23);">"./src/router.json5"</span>,<span style="color: rgb(6,125,23);">"router.json5"</span>],    // 配置打包到HAR产物中的文件
      <span style="color: rgb(135,16,148);">"exclude"</span>: [<span style="color: rgb(6,125,23);">"./config/*"</span>]     // 配置不打包到HAR产物中的文件
    }
  }
}
```
 
> [!NOTE]
> 配置include字段时，以下目录不生效，即不会被打包到产物中：node_modules、oh_modules、.preview、build、.cxx、.test。 配置exclude字段时，以下文件不生效，默认会打包：oh-package.json5。

6. 选中HAR模块的根目录，点击鼠标右键** > 构建模块**启动构建。

  
> [!NOTE]
> 若修改了HAR模块级oh-package.json5文件的version字段，请先执行 构建 > 清理项目 操作，再重新进行构建。


  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/69/v3/AJW6Ls6wSkuDHy9HpZjpOQ/zh-cn_image_0000002779082767.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=A583AF99F5AA1BC4D604B28E55ECA7C74C9D37128F6AF19AC352F9589824BF1E)


  构建完成后，build目录下生成HAR包产物。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/75/v3/jtZ78G4DQvCXqDv3_b-2zw/zh-cn_image_0000002779082755.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=9BC5FE435FA332640F01F6E9D646921D9ABE64875327E87DF9B96FF6A23B493A)


  HAR包产物解压后，结构如下：

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/37/v3/QEMI22CNTXO2XRZ3bhaN8g/zh-cn_image_0000002749483700.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=A03468BDE2AD53A91241441BA74B3163EAF55BD7B85CD4393C11DAAB31D9B4AE)

 
 

## 源码HAR

 

### 以debug模式构建

产物是包含源码的HAR包，其中包含源码、资源文件以及配置文件等，方便开发者进行本地调测，不包含build、node_modules、oh_modules、.cxx、.preview、.hvigor、.gitignore、.ohpmignore、.gitignore/.ohpmignore中配置的文件、cpp工程的CMakeLists.txt。
 
> [!NOTE]
> 源码HAR包中包含源代码，请谨慎分发，避免造成源代码泄露。

1. 在HAR模块的build-profile.json5中，将byteCodeHar设置为false。

  
```json
{
  <span style="color: rgb(102,14,122);">"buildOption"</span>: {
    "arkOptions": {
      "byteCodeHar": false
    }
  }
}
```

2. 点击DevEco Studio界面上方![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/10/v3/tLsIClU-SgOolPKs7FriFA/zh-cn_image_0000002749483706.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=F55F6D0B700AF86B2329DEC43BE46DDB3B37E5A506EDB95E66F9B06C90DEFAF7)右侧的![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/c8/v3/RqTPtcpoQXutNZX3Kd_baw/zh-cn_image_0000002778922913.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=0508FBF3A55A0A51A0DC51D5B814099D6535E329DE644D1E8E19681ECBE82E37)，选择**Product配置**，**构建模式**选择**debug**。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4a/v3/XlLO-ENDSFy6sjDex6Gx9g/zh-cn_image_0000002749483696.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=4D24D2264A07E7C806649A1DEA5975BE18D3FF6E55AAE2B9701C01047949182F)

3. （可选）若部分工程源文件无需构建到HAR包中，可在模块目录下新建.ohpmignore文件，或者在模块目录下的.gitignore文件中，配置打包时要忽略的文件，.ohpmignore文件中支持正则表达式写法，.gitignore文件中支持glob语法。DevEco Studio构建时将过滤掉.ohpmignore或.gitignore文件中所包含的文件/文件夹。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/57/v3/i60Tw7vYQaSasuiZqFLGEg/zh-cn_image_0000002749483690.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=8DD2290EFE952A44ED311B68A4D398A541D5A78CF6442A1E598E82CDA4D6BF61)

4. （可选）如果开发者希望自定义打包到HAR产物中的文件，可在HAR模块的build-profile.json5文件中，配置include或exclude字段，支持glob语法。配置include或exclude字段后，.gitignore和.ohpmignore文件将不再生效。

  
```json
<span style="color: rgb(135,16,148);">"buildOption"</span>: {
  <span style="color: rgb(135,16,148);">"packingOptions"</span>: {
    <span style="color: rgb(135,16,148);">"asset"</span>: {
      <span style="color: rgb(135,16,148);">"include"</span>: [<span style="color: rgb(6,125,23);">"./src/router.json5"</span>,<span style="color: rgb(6,125,23);">"router.json5"</span>],    // 配置打包到HAR产物中的文件
      <span style="color: rgb(135,16,148);">"exclude"</span>: [<span style="color: rgb(6,125,23);">"./config/*"</span>]     // 配置不打包到HAR产物中的文件
    }
  }
}
```
 
> [!NOTE]
> 配置include字段时，以下目录不生效，即不会被打包到产物中：node_modules、oh_modules、.preview、build、.cxx、.test。 配置exclude字段时，以下文件不生效，默认会打包：oh-package.json5。

5. 选中HAR模块的根目录，点击**鼠标右键 > 构建模块**启动构建。

  
> [!NOTE]
> 若修改了HAR模块级oh-package.json5文件的version字段，请先执行 构建 > 清理项目 操作，再重新进行构建。


  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/be/v3/JF74-OXMTo6bmWjoWFHJpw/zh-cn_image_0000002749483698.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=D4C36056CA92E680FF26FDFB42A477A9D8448CF05449949ED5BAF3F2C14DA1D3)


  构建完成后，build目录下生成HAR包产物。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4/v3/VkHglzjgRdKnFCYWkR2GXQ/zh-cn_image_0000002778922917.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=D7D1AC81A983E88DF385D22D1864659C4088DFAEEEB36D7CBA3FE3E2922E06BF)


  HAR包产物解压后，结构如下：

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/71/v3/pOhZm74aQE2G7_OlFQAndg/zh-cn_image_0000002749483702.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=F977CE7113C0CEBF161C1D0371D457DB3F7EB52218009AEC9F9DD53EBD1CBA21)

 
 

### 以release模式构建

DevEco Studio默认不开启混淆，以release模式构建时，构建产物和debug模式相同，请参考[以debug模式构建](#section197792874110)。
 
为保护代码资产，建议开启混淆，开启后，构建产物是包含js中间码的HAR包，其中包含源码混淆后生成的js中间码文件、资源文件、配置文件、readme、changelog声明文件、license证书文件，用于发布到ohpm中心仓。
 1. 在HAR模块的build-profile.json5中，将byteCodeHar设置为false。

  
```json
{
  <span style="color: rgb(102,14,122);">"buildOption"</span>: {
    "arkOptions": {
      "byteCodeHar": false
    }
  }
}
```

2. 点击DevEco Studio界面上方![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/9d/v3/IEm0F0GyRPGT5CS0mzC3hw/zh-cn_image_0000002749323816.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=0F52E6E348B79C14D696EC7D472BB8FF452CC213D7AD1C2D901B5F8B6F5B7043)右侧的![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/83/v3/krfZIYw0S_K1xQO9kx5rqQ/zh-cn_image_0000002749483704.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=CB9D744FDB6A53022CA787BEBDB3E7F21CCABE16523A3793101E9322C2ED1393)，选择**Product配置**，**构建模式**选择**release**。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/8f/v3/L-UEGp9NTLKfz_IpjQsnhg/zh-cn_image_0000002778922907.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=535660360E7839BE521F5F79B99ADE765CA2F8FF312A44CBBA65BCAEB4B0ED49)

3. 在构建模式为release时，为保护代码资产，建议开启混淆，在模块级build-profile.json5文件的release的buildOptionSet配置中，将obfuscation/ruleOptions下的enable字段设置为true。混淆相关能力和具体规则请参考[混淆加固](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-build-obfuscation)。

  
```json
{
  <span style="color: rgb(135,16,148);">"apiType"</span>: <span style="color: rgb(6,125,23);">"stageMode"</span>,
  <span style="color: rgb(135,16,148);">"buildOption"</span>: {
  },
  <span style="color: rgb(135,16,148);">"buildOptionSet"</span>: [
    {
      <span style="color: rgb(135,16,148);">"name"</span>: <span style="color: rgb(6,125,23);">"release"</span>,
      <span style="color: rgb(135,16,148);">"arkOptions"</span>: {
        // 混淆相关参数
        <span style="color: rgb(135,16,148);">"obfuscation"</span>: {
          <span style="color: rgb(135,16,148);">"ruleOptions"</span>: {
            // true表示进行混淆，false表示不进行混淆。
            <span style="color: rgb(135,16,148);">"enable"</span>: <span style="color: rgb(0,51,179);">true</span>,
            // 混淆规则文件
            <span style="color: rgb(135,16,148);">"files"</span>: [
              <span style="color: rgb(6,125,23);">"./obfuscation-rules.txt"</span>
            ]
          },
          // consumerFiles中指定的混淆配置文件会在构建依赖这个library的工程或library时被应用
          <span style="color: rgb(135,16,148);">"consumerFiles"</span>: [
            <span style="color: rgb(6,125,23);">"./consumer-rules.txt"</span>
          ]
        }
      },
    },
  ],
  <span style="color: rgb(135,16,148);">"targets"</span>: [
    {
      <span style="color: rgb(135,16,148);">"name"</span>: <span style="color: rgb(6,125,23);">"default"</span>
    }
  ]
}
```

4. （可选）如果开发者希望自定义打包到HAR产物中的文件，可在HAR模块的build-profile.json5文件中，配置include或exclude字段，支持glob语法。

  
```json
<span style="color: rgb(135,16,148);">"buildOption"</span>: {
  <span style="color: rgb(135,16,148);">"packingOptions"</span>: {
    <span style="color: rgb(135,16,148);">"asset"</span>: {
      <span style="color: rgb(135,16,148);">"include"</span>: [<span style="color: rgb(6,125,23);">"./src/router.json5"</span>,<span style="color: rgb(6,125,23);">"router.json5"</span>],    // 配置打包到HAR产物中的文件
      <span style="color: rgb(135,16,148);">"exclude"</span>: [<span style="color: rgb(6,125,23);">"./config/*"</span>]     // 配置不打包到HAR产物中的文件
    }
  }
}
```
 
> [!NOTE]
> 配置include字段时，以下目录不生效，即不会被打包到产物中：node_modules、oh_modules、.preview、build、.cxx、.test。 配置exclude字段时，以下文件不生效，默认会打包：oh-package.json5。

5. 选中HAR模块的根目录，点击鼠标右键** > 构建模块**启动构建。

  
> [!NOTE]
> 若修改了HAR模块级oh-package.json5文件的version字段，请先执行 构建 > 清理项目 操作，再重新进行构建。


  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/b9/v3/iAPyezDdTJmOsmUA6L4z8A/zh-cn_image_0000002778922909.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=BE97C5E657BCF05F45BF2071F20FE874847C72168FBBD43C3EDA716CE57E0A6E)


  构建完成后，build目录下生成HAR包产物。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/58/v3/Uk6MJPK5SeSxHTG7ZnKgIA/zh-cn_image_0000002778922919.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=C546D478D04BA5732D65C7D86C62516410C146EEE655967D68869CBB67C04E01)


  HAR包产物解压后，结构如下：

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/5b/v3/_-IScr-vSY6qRZLuYDuSGw/zh-cn_image_0000002749323818.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=B0629905A654B39F1D7AEDDA0D75D3B828DA0DB6DB53DF8638BB96649DD001D2)

 
 

## 多HAR合并打包

SDK厂商在对外发布SDK（HAR包）时，有时需要隐藏内部实现细节及依赖，仅暴露必要的接口。Hvigor支持将字节码HAR及其所有依赖合并打包，生成一个无外部依赖、可直接使用的独立HAR包。
 
 

### 配置方法

在HAR模块的build-profile.json5文件中，配置bundle字段可以实现多HAR合并打包的能力。bundle下包含bundledDeclare和bundledAllDependencies两个字段，是[bundledDependencies](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-hvigor-build-profile#section8368152412552)的增强版。使用时，不能同时配置bundle和bundledDependencies。
 
```json
// HAR模块build-profile.json5
"buildOption": {
  "arkOptions": {
    "bundle": {
      "bundledDeclare": true,
      "bundledAllDependencies": true
    }
  }
}
```
  


> [!NOTE] 说明
> bundledDeclare开启后，产物HAR中，默认只会生成oh-package.json5中main字段和oh-exports字段所指向源码文件的声明文件。如未配置oh-exports字段，则只生成main字段源码的声明文件。


| 字段名称 | 类型 | 可选/必选 | 含义 |
| --- | --- | --- | --- |
| bundledDeclare | 布尔值 | 可选 | 构建字节码HAR或HSP时，是否生成bundle化的声明文件。 true：生成。false（缺省默认值）：不生成。 |
| bundledAllDependencies | 布尔值 | 可选 | 构建字节码HAR时，是否将所有依赖打包到产物中。 true：打包。false（缺省默认值）：不打包。 |
 
 
> [!NOTE]
> bundledAllDependencies会将dependencies和dynamicDependencies所有依赖都打包，而bundledDependencies只会将dependencies和dynamicDependencies依赖的源码HAR打包。 bundledAllDependencies为true，devDependencies中配置的HAR包的资源/so不会打包。 bundledAllDependencies为true，bundledDeclare也必须配置为true。 bundledAllDependencies为true，且hvigor-config.json5的ohos.byteCodeHar.integratedOptimization为true时，工程级oh-package.json5中的本地模块依赖的资源/so不会打包。 bundledAllDependencies为true，依赖中不支持配置HSP类型的依赖。 bundledAllDependencies为true，若依赖没有被调用，则最终会被裁剪，不会打包到最终的HAR中。

 
 

### 使用效果说明

关于bundledDeclare字段的使用效果，示例代码如下：
 
```json
// oh-package.json5
"dependencies": {
  "shop": "1.0.0"
}
```
 

```ArkTS
// Index.ets
export { live } from './src/main/ets/components/Live';
export { shop } from 'shop';
```
 
 
- bundledDeclare不配置，或配置为false时，编译的字节码HAR或者编译HSP生成的HAR中的声明文件如下：
```ArkTS
// Index.d.ets
export { live } from './src/main/ets/components/Live';
export { shop } from 'shop';
```

- 配置bundledDeclare为true后编译：
```ArkTS
// Index.d.ets
export declare function live(game: string): void;
export declare function shop(product: string): void;
```


 
 

关于bundledAllDependencies字段的使用效果，示例代码如下，以live模块为例：
```json
// oh-package.json5
"dependencies": {
  "shop": "1.0.0"
}
```
 
 

```ArkTS
// Index.ets
export { live } from './src/main/ets/components/Live';
export { shop } from 'shop';
```
 
 
将bundledAllDependencies配置为true（此时bundledDeclare也必须配置为true）编译，除了Index.d.ets会被bundle合并外，依赖的shop源代码文件也会被合并到live的modules.abc中，资源文件/so文件也会合并打包到live包中。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/27/v3/Ch-p3nLERiam1qfKAkhVLw/zh-cn_image_0000002749323830.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=E82C1912CFF027061CE8B7C11B438400CCAFAABDF784F1D729FE35943C05309B)

 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/e0/v3/PclKaYm7Td-_pELYZNOBpQ/zh-cn_image_0000002778922905.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=F89E169E670103BF0E5E340DB551AC19D31F4FA5F626D46C5F7B31D5A3FD9EDE)

 
 

配置bundledAllDependencies为true后，HAR包的oh-package.json5中的dependencies也会被消除：
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/63/v3/YCogA6CsRWm54nhD-DpoTw/zh-cn_image_0000002779082763.png?HW-CC-KV=V1&HW-CC-Date=20261009T012530Z&HW-CC-Expire=86400&HW-CC-Sign=D114A60A6829BCAD4270C60754E00DADA54BBBA94319ECB1116900B0F8FF08B1)
