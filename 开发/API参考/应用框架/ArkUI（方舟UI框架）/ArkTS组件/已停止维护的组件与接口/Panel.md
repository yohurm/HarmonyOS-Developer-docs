# Panel

更新时间：2026-09-09 06:54:05

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/ts-container-panel
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

可滑动面板，提供一种轻量的内容展示窗口，方便在不同尺寸中切换。

> [!NOTE]
> 从API version 12开始，该组件不再维护，推荐使用通用属性 bindSheet 。 该组件从API version 7开始支持。后续版本如有新增内容，则采用上角标单独标记该内容的起始版本。



## 子组件


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

可以包含子组件。

> [!NOTE]
> 子组件类型：系统组件和自定义组件，支持渲染控制类型（ if/else 、 ForEach 和 LazyForEach ）。




## 接口


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

Panel(show: boolean)

滑动面板组件。

> [!NOTE]
> 从API version 7开始支持，从API version 12开始废弃。建议使用 bindSheet 替代。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| show | boolean | 是 | 控制Panel显示或隐藏，true表示显示面板，false表示隐藏面板。 说明： 如果设置为false时，则不占位隐藏。Visibility.None或show之间有一个生效时，都会生效不占位隐藏。 属性show的优先级高于此参数，当属性show被设置时，本参数可能不生效。 |




## 属性


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

除支持[通用属性](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/ts-component-general-attributes)外，还支持以下属性：



### type


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type(value: PanelType)

可滑动面板的类型。type属性值制约其他属性的使用：当type为Minibar时，PanelMode.Half不生效；当type为Temporary时，PanelMode.Mini不生效；当type为CUSTOM时，不支持尺寸切换效果，需配合customHeight属性使用；当type为Foldable时，所有PanelMode值均可用，可配合fullHeight、halfHeight、miniHeight属性设置各状态高度。

> [!NOTE]
> 从API version 7开始支持，从API version 12开始废弃。建议使用 SheetOptions 中的preferType替代。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| value | PanelType | 是 | 设置可滑动面板的类型。 默认值：PanelType.Foldable |




### mode


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

mode(value: PanelMode)

可滑动面板的初始状态。

> [!NOTE]
> 从API version 7开始支持，从API version 12开始废弃。建议使用 SheetOptions 中的preferType替代。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| value | PanelMode | 是 | 设置可滑动面板的初始状态。 Minibar类型默认值：PanelMode.Mini；其余类型默认值：PanelMode.Half 从API version 10开始，该属性支持$$双向绑定变量。 |




### dragBar


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

dragBar(value: boolean)

设置是否存在控制条。

> [!NOTE]
> 从API version 7开始支持，从API version 12开始废弃。建议使用 SheetOptions 中的dragBar替代。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| value | boolean | 是 | 设置是否存在控制条，true表示存在，false表示不存在。 默认值：true |




### customHeight10+


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

customHeight(value: Dimension | PanelHeight)

指定PanelType.CUSTOM状态下的高度。此属性仅在[type](#type)设置为PanelType.CUSTOM时生效，使用PanelHeight.WRAP_CONTENT时高度自适应内容，使用Dimension值时设置固定高度。

> [!NOTE]
> 从API version 10开始支持，从API version 12开始废弃。建议使用 SheetOptions 中的height替代。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| value | Dimension \| PanelHeight | 是 | 指定PanelType.CUSTOM状态下的高度。 默认值：0 说明： 不支持设置百分比，传入百分比时不生效。传入负数时不生效。 |




### fullHeight


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

fullHeight(value: number | string)

指定PanelMode.Full状态下的高度。

> [!NOTE]
> 从API version 7开始支持，从API version 12开始废弃。建议使用 SheetOptions 中的height替代。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| value | number \| string | 是 | 指定PanelMode.Full状态下的高度。 默认值：当前组件主轴大小减去8vp空白区 单位：vp 说明： 不支持设置百分比。 |




### halfHeight


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

halfHeight(value: number | string)

指定PanelMode.Half状态下的高度。

> [!NOTE]
> 此属性仅在type为Foldable或Temporary时生效。当type为Minibar时，Half模式不生效，halfHeight设置无效。 从API version 7开始支持，从API version 12开始废弃。建议使用 SheetOptions 中的height替代。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| value | number \| string | 是 | 指定PanelMode.Half状态下的高度。 默认值：当前组件主轴大小的一半。 单位：vp 说明： 不支持设置百分比。 |




### miniHeight


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

miniHeight(value: number | string)

指定PanelMode.Mini状态下的高度。

> [!NOTE]
> 此属性仅在type为Minibar或Foldable时生效。当type为Temporary时，Mini模式不生效，miniHeight设置无效。 从API version 7开始支持，从API version 12开始废弃。建议使用 SheetOptions 中的height替代。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| value | number \| string | 是 | 指定PanelMode.Mini状态下的高度。 默认值：48 单位：vp 说明： 不支持设置百分比。 |




### show


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

show(value: boolean)

当滑动面板弹出时调用。

> [!NOTE]
> 从API version 7开始支持，从API version 12开始废弃。建议使用 SheetOptions 中的isShow替代。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| value | boolean | 是 | 当滑动面板弹出时调用，true显示面板，false不显示面板。 默认值：true 说明： 该属性的优先级高于参数show。 |




### backgroundMask9+


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

backgroundMask(color: ResourceColor)

指定Panel的背景蒙层。

> [!NOTE]
> 从API version 9开始支持，从API version 12开始废弃。建议使用 SheetOptions 中的maskColor替代。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| color | ResourceColor | 是 | 指定Panel的背景蒙层。 默认值：'#08182431' |




### showCloseIcon10+


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

showCloseIcon(value: boolean)

设置是否显示关闭图标。

> [!NOTE]
> 从API version 10开始支持，从API version 12开始废弃。建议使用 SheetOptions 中的showClose替代。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| value | boolean | 是 | 设置是否显示关闭图标，true表示显示，false表示不显示。 默认值：false |




## PanelType枚举说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

> [!TIP]
> 从API version 7开始支持，从API version 12开始废弃。建议使用 SheetSize 替代。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full


| 名称 | 值 | 说明 |
| --- | --- | --- |
| Minibar | 0 | 提供Minibar和类全屏展示切换效果。 |
| Foldable | 1 | 内容始终展示，提供大（类全屏）、中（类半屏）、小三种尺寸展示切换效果。 |
| Temporary | 2 | 内容临时展示，提供大（类全屏）、中（类半屏）两种尺寸展示切换效果。 |
| CUSTOM10+ | 3 | 配置自适应内容高度，不支持尺寸切换效果。 |




## PanelMode枚举说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

> [!NOTE]
> 从API version 7开始支持，从API version 12开始废弃。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full


| 名称 | 值 | 说明 |
| --- | --- | --- |
| Mini | 0 | 类型为Minibar和Foldable时，为最小状态；类型为Temporary，则不生效。 |
| Half | 1 | 类型为Foldable和Temporary时，为类半屏状态；类型为Minibar，则不生效。 |
| Full | 2 | 类型为Minibar、Foldable和Temporary时，为类全屏状态；类型为CUSTOM，则不生效。 |




## PanelHeight10+枚举说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

> [!TIP]
> 从API version 10开始支持，从API version 12开始废弃。建议使用 SheetSize 替代。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full


| 名称 | 值 | 说明 |
| --- | --- | --- |
| WRAP_CONTENT | 'wrapContent' | PanelType的类型为CUSTOM时，自适应内容高度。 |




## 事件


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

除支持[通用事件](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/ts-component-general-events)外，还支持以下事件：



### onChange


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

onChange(event: (width: number, height: number, mode: PanelMode) => void)

当可滑动面板发生状态变化时触发。与onHeightChange的区别：onChange在面板模式切换时触发，返回宽高和模式信息；onHeightChange在面板高度变化时触发，仅返回高度值。需要感知模式切换时使用onChange，仅需感知高度变化时使用onHeightChange。

> [!NOTE]
> 从API version 7开始支持，从API version 12开始废弃。建议使用 SheetOptions 中的onTypeDidChange替代。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| width | number | 是 | 内容区的宽度值，单位：vp。 |
| height | number | 是 | 内容区的高度值，单位：vp。 当dragBar属性为true时，Panel本身的高度值为dragBar高度加上内容区高度。 |
| mode | PanelMode | 是 | 面板的状态。 |




### onHeightChange9+


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

onHeightChange(callback: (value: number) => void)

当可滑动面板发生高度变化时触发。

> [!NOTE]
> 从API version 9开始支持，从API version 12开始废弃。建议使用 SheetOptions 中的onHeightDidChange替代。


**元服务API：** 从API version 11开始，该接口支持在元服务中使用。

**系统能力：** SystemCapability.ArkUI.ArkUI.Full

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| value | number | 是 | 内容区的高度值，默认返回值单位为px。 当dragBar属性为true时，Panel本身的高度值为dragBar高度加上内容区高度。 因用户体验设计原因，Panel最高只能滑到fullHeight-8vp。 |




## 示例


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```ArkTS
// xxx.ets
@Entry
@Component
struct PanelExample {
  @State show: boolean = false

  build() {
    Column() {
      Text('2021-09-30    Today Calendar: 1.afternoon......Click for details')
        .width('90%')
        .height(50)
        .borderRadius(10)
        .backgroundColor(0xFFFFFF)
        .padding({ left: 20 })
        .onClick(() => {
          this.show = !this.show;
        })
      Panel(this.show) { // 展示日程
        Column() {
          Text('Today Calendar')
          Divider()
          Text('1. afternoon 4:00 The project meeting')
        }
      }
      .type(PanelType.Foldable)
      .mode(PanelMode.Half)
      .dragBar(true) // 默认开启
      .halfHeight(500) // 设置半屏高度为500，默认为当前组件主轴大小的一半
      .showCloseIcon(true) // 显示关闭图标
      .onChange((width: number, height: number, mode: PanelMode) => {
        console.info(`width:${width},height:${height},mode:${mode}`);
      })
    }.width('100%').height('100%').backgroundColor(0xDCDCDC).padding({ top: 5 })
  }
}
```


![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/c6/v3/REAStaGWSKKTcPRo_HUWiw/zh-cn_image_0000002747213083.gif?HW-CC-KV=V1&HW-CC-Date=20260911T073114Z&HW-CC-Expire=86400&HW-CC-Sign=2C369FB3FA37B52A3E814A1DD22962E3C86FD23D5A7646110A821CCC4AF6240A)
