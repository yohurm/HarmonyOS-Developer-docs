# Ability Kit

更新时间：2026-08-29 09:40:02

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-releases/js-apidiff-abilitykit-7003

| 操作 | 旧版本 | 新版本 | d.ts文件 |
| --- | --- | --- | --- |
| syscap变更 | 类名：systemConfiguration； API声明：interface UpdatedCallback 差异内容：SystemCapability.Ability.AbilityRuntime.AbilityCore | 类名：systemConfiguration； API声明：interface UpdatedCallback 差异内容：SystemCapability.Ability.AbilityRuntime.Core | api/@ohos.app.ability.systemConfiguration.d.ts |
| 新增错误码 | 类名：AtManager； API声明：requestPermissionOnSetting(context: Context, permissionList: Array&lt;Permissions&gt;): Promise<Array&lt;GrantStatus&gt;>; 差异内容：NA | 类名：AtManager； API声明：requestPermissionOnSetting(context: Context, permissionList: Array&lt;Permissions&gt;): Promise<Array&lt;GrantStatus&gt;>; 差异内容：12100010 | api/@ohos.abilityAccessCtrl.d.ts |
| 新增API | NA | 类名：global； API声明：declare namespace appMemoryOptimizer 差异内容：declare namespace appMemoryOptimizer | api/@ohos.app.ability.appMemoryOptimizer.d.ts |
| 新增API | NA | 类名：appMemoryOptimizer； API声明：function evictFilePages(fileNames: Array&lt;string&gt;): Promise&lt;void&gt;; 差异内容：function evictFilePages(fileNames: Array&lt;string&gt;): Promise&lt;void&gt;; | api/@ohos.app.ability.appMemoryOptimizer.d.ts |
| 新增API | NA | 类名：appMemoryOptimizer； API声明：function evictModuleFilePages(moduleNames: Array&lt;string&gt;): Promise&lt;void&gt;; 差异内容：function evictModuleFilePages(moduleNames: Array&lt;string&gt;): Promise&lt;void&gt;; | api/@ohos.app.ability.appMemoryOptimizer.d.ts |
| 新增API | NA | 类名：AbilityStage； API声明：onAboutToCreateAbilityAsync(): Promise&lt;void&gt;; 差异内容：onAboutToCreateAbilityAsync(): Promise&lt;void&gt;; | api/@ohos.app.ability.AbilityStage.d.ts |
| 新增kit | 类名：global； API声明： 差异内容：NA | 类名：global； API声明：api@ohos.app.ability.appMemoryOptimizer.d.ts 差异内容：AbilityKit | api/@ohos.app.ability.appMemoryOptimizer.d.ts |
