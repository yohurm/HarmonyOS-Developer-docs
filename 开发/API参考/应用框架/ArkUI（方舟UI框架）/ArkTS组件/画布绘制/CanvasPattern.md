# CanvasPattern

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/ts-components-canvas-canvaspattern
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

CanvasPattern对象，使用[createPattern](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/ts-components-canvas-common-method#createpattern)方法创建，通过指定图像和重复方式生成图片填充的模板，适用于需要在Canvas中实现图案填充或背景纹理的场景，可简化图案填充的实现并提高绘制效率。
 
> [!NOTE]
> 本模块首批接口从API version 8开始支持。后续版本的新增接口，采用上角标单独标记接口的起始版本。

  

## 方法


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### setTransform


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

setTransform(transform?: Matrix2D): void
 
使用Matrix2D对象作为参数，对当前CanvasPattern进行矩阵变换。适用于需要对图案填充进行平移、缩放、旋转等几何变换的场景。不传参时，不对CanvasPattern做矩阵变换处理。
 
**卡片能力：** 从API version 9开始，该接口支持在ArkTS卡片中使用。
 
**元服务API：** 从API version 11开始，该接口支持在元服务中使用。
 
**系统能力：** SystemCapability.ArkUI.ArkUI.Full
 
**参数：**
  

| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| transform | Matrix2D | 否 | 转换矩阵，用于对CanvasPattern进行平移、缩放、旋转等几何变换。 说明：参数为undefined或null时不做矩阵变换处理。 默认值：null |
 
 
  

## 示例


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

通过createPattern创建CanvasPattern对象，在onReady回调和按钮点击时分别设置matrix参数，并调用setTransform方法进行矩阵变换。
 
> [!NOTE]
> 此示例的资源不在src > main > resource目录下，从DevEco Studio 6.0.0 Beta2版本开始，新建工程或模块时，默认创建的模块不会对非resources目录下的资源进行打包，需使能相关开关：模块的build-profile.json5中buildOption > resOptions > copyCodeResource > enable设置为true，详见resOptions中 copyCodeResource 相关介绍。

 
```ArkTS
// xxx.ets
@Entry
@Component
struct CanvasPatternPage {
  private settings: RenderingContextSettings = new RenderingContextSettings(true);
  private context: CanvasRenderingContext2D = new CanvasRenderingContext2D(this.settings);
  private matrix: Matrix2D = new Matrix2D();
  // "common/pattern.jpg"需要替换为开发者所需的图像资源文件
  private img: ImageBitmap = new ImageBitmap('common/pattern.jpg');
  private pattern: CanvasPattern | null = null;

  build() {
      Column() {
        Button('Click to set transform')
          .onClick(() => {
            this.matrix.scaleY = 1
            this.matrix.scaleX = 1
            this.matrix.translateX = 50
            this.matrix.translateY = 200
            if (this.pattern) {
              this.pattern.setTransform(this.matrix)
            }
            this.context.fillRect(0, 0, 480, 720)
          })
          .width('45%')
          .margin('5px')
        Canvas(this.context)
          .width('100%')
          .height('80%')
          .backgroundColor('#FFFFFF')
          .onReady(() => {
            this.pattern = this.context.createPattern(this.img, 'no-repeat')
            this.matrix.scaleY = 0.5
            this.matrix.scaleX = 0.5
            this.matrix.translateX = 50
            this.matrix.translateY = 50
            if (this.pattern) {
              this.context.fillStyle = this.pattern
              this.pattern.setTransform(this.matrix)
            }
            this.context.fillRect(0, 0, 480, 720)
          })
      }
      .width('100%')
      .height('100%')
  }
}
```
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/82/v3/iKdgoN6nSrS4O2pGg2H2zQ/zh-cn_image_0000002747212837.gif?HW-CC-KV=V1&HW-CC-Date=20260911T073110Z&HW-CC-Expire=86400&HW-CC-Sign=D682502F96A7FF3A81075450E4942B7F2C5E062A5B74026B9AE560BE17DBC800)
