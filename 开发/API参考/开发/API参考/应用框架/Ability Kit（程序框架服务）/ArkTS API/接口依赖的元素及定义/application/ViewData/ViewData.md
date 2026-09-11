# ViewData

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/js-apis-inner-application-viewdata
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

自动填充的视图数据信息。
 
**起始版本：** 26.0.0
  

## 导入模块


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
import { autoFillManager } from '@kit.AbilityKit';
```
 
  

## ViewData


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

**起始版本：** 26.0.0
 
**元服务API**：从API版本26.0.0开始，该接口支持在元服务中使用。
 
**系统能力**：SystemCapability.Ability.AbilityRuntime.AbilityCore
 
**模型约束**：此接口仅可在Stage模型下使用。
  

| 名称 | 类型 | 只读 | 可选 | 说明 |
| --- | --- | --- | --- | --- |
| bundleName | string | 否 | 否 | 应用名称。 |
| pageUrl | string | 否 | 否 | 页面的url。 |
| pageNodeInfos | Array&lt;PageNodeInfo&gt; | 否 | 否 | 页面节点的信息。 |
| pageRect | AutoFillRect | 否 | 否 | 页面的位置坐标与宽高信息。在PC/2in1设备上，密码保险箱以弹窗形式展示，为保证弹窗位置跟随输入框，left和top需置为0。 |
