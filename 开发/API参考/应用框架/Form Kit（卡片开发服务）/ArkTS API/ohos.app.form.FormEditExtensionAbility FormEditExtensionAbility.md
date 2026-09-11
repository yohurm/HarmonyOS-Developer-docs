# @ohos.app.form.FormEditExtensionAbility (FormEditExtensionAbility)

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/js-apis-app-form-formeditextensionability
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

FormEditExtensionAbility模块提供卡片编辑功能，支持用户在卡片提供方应用内编辑卡片内容，适用于需要动态更新卡片展示信息、实现卡片个性化配置的场景。继承自[UIExtensionAbility](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/js-apis-app-ability-uiextensionability)。
 
> [!NOTE]
> 本模块首批接口从API version 18开始支持。后续版本的新增接口，采用上角标单独标记接口的起始版本。 本模块接口仅可在Stage模型下使用。

  

## 导入模块


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
import { FormEditExtensionAbility } from '@kit.FormKit';
```
 
  

## FormEditExtensionAbility


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

提供卡片编辑功能，继承此类并实现生命周期方法后，可实现卡片编辑界面，用于在用户长按卡片等场景下触发卡片编辑。
 
  

### 属性


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

**模型约束：** 此接口仅可在Stage模型下使用。
 
**系统能力：** SystemCapability.Ability.Form
  

| 名称 | 类型 | 只读 | 可选 | 说明 |
| --- | --- | --- | --- | --- |
| context | FormEditExtensionContext | 否 | 否 | FormEditExtensionAbility的上下文环境，FormEditExtensionContext继承自UIExtensionContext。提供拉起编辑页面的能力。 |
