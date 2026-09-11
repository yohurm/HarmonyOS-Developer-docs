# 如何在TabBar页签栏添加其他组件

更新时间：2026-08-26 00:50:37

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-faqs/faqs-arkui-1074

## 问题现象

为了提升用户体验和界面功能性，开发者往往会在TabBar页签栏中添加其他组件（如按钮、图标、通知角标等），以下是在TabBar两侧添加其他组件的常见写法：
 
- 方案一：TabBar叠加overlay浮层效果。
- 方案二：利用Stack组件，在自定义TabBar上堆叠其他组件。
- 方案三：使用Row组件自定义行内布局。

 
 

## 背景知识

- [Tabs组件](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/ts-container-tabs)：通过页签进行内容视图切换的容器组件，每个页签对应一个内容视图。
- [tabBar](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/ts-container-tabcontent#tabbar)：设置TabBar上显示内容。
- [overlay](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/ts-universal-attributes-overlay#overlay)：在当前组件上，增加遮罩文本或者叠加自定义组件以及ComponentContent作为该组件的浮层。浮层的定位同样基于当前组件进行计算。
- [Stack组件](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/ts-container-stack)：堆叠容器，子组件按照顺序依次入栈，后一个子组件覆盖前一个子组件。
- [zIndex](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/ts-universal-attributes-z-order#zindex)：设置组件的堆叠顺序。
- [Row组件](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/ts-container-row)：沿水平方向布局的容器。

 
 

## 解决方案

本文将基于上述场景，逐一阐述其具体实现方式。
  

| 实现方案 | 方案描述 | 适用场景 |
| --- | --- | --- |
| 方案一 | TabBar叠加overlay浮层效果。 | 实现简单，无需自定义TabBar；且使用overlay可以实现动态显示而不必重新渲染整个TabBar。 |
| 方案二 | 利用Stack组件，在自定义TabBar上堆叠其他组件。 | 当需要在TabBar的特定位置添加固定的功能按钮或图标时，Stack组件可以方便地实现这一需求，而不会影响TabBar的其他部分。 |
| 方案三 | 使用Row组件自定义行内布局。 | 当需要完全自定义TabBar的布局时，Row组件可以提供更大的灵活性。 |
 
 
- **方案一：TabBar叠加overlay浮层效果。**在当前Tabs组件上，可以叠加按钮或图标作为TabBar的浮层，达到页签栏添加其他组件的效果，原理如下图：

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/85/v3/4Rlwx484RE2_y7LyZZb6lQ/zh-cn_image_0000002658806493.png?HW-CC-KV=V1&HW-CC-Date=20260911T072742Z&HW-CC-Expire=86400&HW-CC-Sign=BE38461503589739853CDE3BD5645FBD3CB29997CF829E1C5795F3FA16592C86)


  实现步骤如下：

1. 将左侧的按钮与右侧的图标放置于Flex布局容器中，并设置组件内布局为两端对齐；

2. 为了叠加后TabBar依旧可触发点击效果，需给Flex组件设置属性.hitTestBehavior(HitTestMode.Transparent)，配置浮层不阻塞交互；

3. 将Flex组件通过overlay属性叠加在TabBar上。

  实现代码如下：

  
```text
import { promptAction } from '@kit.ArkUI';
import { BusinessError } from '@kit.BasicServicesKit';

@Entry
@Component
struct TabBarOverlay {
  tabArr: string[] = ['首页', '商城', '账号'];
  @State currentIndex: number = 0;

  @Builder
  tabBuilder(index: number, name: string) {
    Column() {
      Text(name)
        .width('74vp')
        .height('36vp')
        .textAlign(TextAlign.Center)
        .textVerticalAlign(TextVerticalAlign.CENTER)
        .fontColor(this.currentIndex === index ? '#e6000000' : '#99000000')
        .fontSize(14)
        .fontWeight(this.currentIndex === index ? 500 : 400)
        .lineHeight(40)
        .backgroundColor(this.currentIndex === index ? Color.White : '#00000000')
        .borderRadius('50vp');
    }
    .backgroundColor('#0d000000')
    .borderRadius({
      topLeft: index === 0 ? 50 : 0,
      bottomLeft: index === 0 ? 50 : 0,
      topRight: index === 2 ? 50 : 0,
      bottomRight: index === 2 ? 50 : 0
    })
    .margin({ top: 5 })
    .padding(2);
  }

<em>  // 设置浮层</em>
  @Builder
  tabOverlay() {
    Flex({
      justifyContent: FlexAlign.SpaceBetween,
      direction: FlexDirection.Row,
      alignItems: ItemAlign.Center
    }) {
      Image($r('sys.media.ohos_ic_public_arrow_left'))<em> // 开发者可根据需求更换其它图片资源</em>
        .width(30)
        .height(30)
        .onClick(() => {
          try {
            this.getUIContext().getPromptAction().showToast({
              message: '触发开发者自定义事件',
              duration: 2000,
              showMode: promptAction.ToastShowMode.TOP_MOST,
              bottom: 85
            });
          } catch (error) {
            let message = (error as BusinessError).message;
            let code = (error as BusinessError).code;
            console.error(`showToast args error code is ${code}, message is ${message}`);
          }
        });
      Image($r('sys.media.ohos_ic_public_more'))<em> // 开发者可根据需求更换其它图片资源</em>
        .width(30)
        .height(30)
        .onClick(() => {
          try {
            this.getUIContext().getPromptAction().showToast({
              message: '触发开发者自定义事件',
              duration: 2000,
              showMode: promptAction.ToastShowMode.TOP_MOST,
              bottom: 85
            });
          } catch (error) {
            let message = (error as BusinessError).message;
            let code = (error as BusinessError).code;
            console.error(`showToast args error code is ${code}, message is ${message}.`);
          }
        });
    }
    .padding({ left: 20, right: 20 })
    .width('100%')
    .height(56)
    .hitTestBehavior(HitTestMode.Transparent);<em> // 配置浮层不阻塞交互</em>
  }

  build() {
    Column() {
      Tabs() {
        ForEach(this.tabArr, (item: string, index: number) => {
          TabContent() {
            Column()
              .width('100%')
              .height('100%');
          }
          .expandSafeArea([SafeAreaType.SYSTEM], [SafeAreaEdge.BOTTOM])
          .backgroundColor('#FFFFFF')
          .tabBar(this.tabBuilder(index, item));
        });
      }
      .width('100%')
      .height('100%')
      .barMode(BarMode.Scrollable)
      .barWidth(250)
      .overlay(this.tabOverlay(), { align: Alignment.Top })
      .onChange((index: number) => {
        this.currentIndex = index;
      });
    };
  }
}
```
 实现效果如下：

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/7b/v3/9J4-KgPsSku2TglbSp6wAw/zh-cn_image_0000002628567142.png?HW-CC-KV=V1&HW-CC-Date=20260911T072742Z&HW-CC-Expire=86400&HW-CC-Sign=F542F7346D5AD03A93121F607A68927BCD4BC9D9D38AAA1EC10CE1A219D1FAD0)

- **方案二：利用Stack组件，在自定义TabBar上堆叠其他组件**。利用堆叠容器，在原本的TabBar基础上放置其他组件，原理如下图：

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/38/v3/erhqAdmFRSKi3f2Ygabikw/zh-cn_image_0000002658926447.png?HW-CC-KV=V1&HW-CC-Date=20260911T072742Z&HW-CC-Expire=86400&HW-CC-Sign=4B124E969AA4B2748EE2994B2CCE07A39909988B0D41B9F8A818CDC0D5482FDA)


  实现步骤如下：

1. 设置Stack组件，依次放入Image组件和Tabs组件；

2. 设置Image组件的zIndex值大于Tabs组件。

  实现代码如下：

  
```text
import { promptAction } from '@kit.ArkUI';
import { BusinessError } from '@kit.BasicServicesKit';

@Entry
@Component
struct TabBarStack {
  @State selectedIndex: number = 0;
  private controller: TabsController = new TabsController();

  @Builder
  tabBuilder(index: number, name: string) {
    Column() {
      Text(name)
        .width('80vp')
        .height('36vp')
        .textAlign(TextAlign.Center)
        .textVerticalAlign(TextVerticalAlign.CENTER)
        .fontColor(this.selectedIndex === index ? '#e6000000' : '#99000000')
        .fontSize(14)
        .fontWeight(this.selectedIndex === index ? 500 : 400)
        .lineHeight(40)
        .backgroundColor(this.selectedIndex === index ? Color.White : '#00000000')
        .borderRadius('50vp');
    }
    .backgroundColor('#0d000000')
    .borderRadius({
      topLeft: index === 0 ? 50 : 0,
      bottomLeft: index === 0 ? 50 : 0,
      topRight: index === 2 ? 50 : 0,
      bottomRight: index === 2 ? 50 : 0
    })
    .margin({ top: 5 })
    .padding(2)
    .onClick(() => {
      this.controller.changeIndex(index);
      this.selectedIndex = index;
    });
  }

  build() {
    Stack({ alignContent: Alignment.TopStart }) {
      Image($r('sys.media.ohos_ic_public_arrow_left'))<em> // 开发者自定义图片资源</em>
        .width(32)
        .height(32)
        .offset({ top: 15, left: 16 })
        .zIndex(1)
        .onClick(() => {
          try {
            this.getUIContext().getPromptAction().showToast({
              message: '触发开发者自定义事件',
              duration: 2000,
              showMode: promptAction.ToastShowMode.TOP_MOST,
              bottom: 85
            });
          } catch (error) {
            let message = (error as BusinessError).message;
            let code = (error as BusinessError).code;
            console.error(`showToast args error code is ${code}, message is ${message}`);
          }
        });

      Tabs({ controller: this.controller }) {
        TabContent() {
          Column()
            .width('100%')
            .height('100%');
        }.tabBar(this.tabBuilder(0, '首页'))
        .expandSafeArea([SafeAreaType.SYSTEM], [SafeAreaEdge.BOTTOM])
        .backgroundColor('#FFFFFF');

        TabContent() {
          Column()
            .width('100%')
            .height('100%');
        }
        .tabBar(this.tabBuilder(1, '商城'))
        .expandSafeArea([SafeAreaType.SYSTEM], [SafeAreaEdge.BOTTOM])
        .backgroundColor('#FFFFFF');

        TabContent() {
          Column()
            .width('100%')
            .height('100%');
        }
        .tabBar(this.tabBuilder(2, '我的'))
        .expandSafeArea([SafeAreaType.SYSTEM], [SafeAreaEdge.BOTTOM])
        .backgroundColor('#FFFFFF');
      }
      .barWidth(250)
      .onAnimationStart((index: number, targetIndex: number) => {
        if (index === targetIndex) {
          return;
        }
        this.selectedIndex = targetIndex;
      })
    <em>  // 设置Tabs层级小于Image组件</em>
      .zIndex(-1);
    }.width('100%').height('100%');
  }
}
```
 实现效果如下：

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/48/v3/U9b63sAnT5WBZ5iZK-Svag/zh-cn_image_0000002628407236.png?HW-CC-KV=V1&HW-CC-Date=20260911T072742Z&HW-CC-Expire=86400&HW-CC-Sign=CD31F6DF56AFFAEFE746286F2FFC8563B7FC71DFC001AD0FF4B77A94063BAF98)


  更丰富的实现效果请参考：[可滚动Tabs页签栏+更多按钮](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/arkts-navigation-tabs#可滚动tabs页签栏更多按钮)。
- **方案三：使用Row组件自定义行内布局**。通过Row组件，自行设置TabBar行内组件的组成效果，原理如下图：

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/bf/v3/8llxx_eNRBaJzNUpIgiChw/zh-cn_image_0000002658806495.png?HW-CC-KV=V1&HW-CC-Date=20260911T072742Z&HW-CC-Expire=86400&HW-CC-Sign=26983567EB6E8DD998C78FD1CEAC31FA4841632F8A790F4F22123A5A9B68E9DB)


  实现步骤如下：

1. 使用Row组件作为容器，包裹Scroll和Button两个子组件；

2. 设置Scroll组件的布局权重[layoutWeight](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/ts-universal-attributes-size#layoutweight)为1，Button优先占位，Scroll占据剩余宽度；

3. 将自定义的TabBar放入Scroll组件中，使其始终位于左侧滚动区域内，从而实现TabBar页签栏添加其他组件的效果。

  实现代码如下：

  
```text
import { promptAction } from '@kit.ArkUI';
import { BusinessError } from '@kit.BasicServicesKit';

@Entry
@Component
struct TabBarRow {
  tabName: Array<string> = ['首页', '商城', '详情'];
  fontColor: string = '#000000';
  @State selectedIndex: number = 0;
  private controller: TabsController = new TabsController();

  @Builder
  tabBuilder(index: number, name: string) {
    Column() {
      Column() {
        Text(name)
          .width('80vp')
          .height('36vp')
          .textAlign(TextAlign.Center)
          .textVerticalAlign(TextVerticalAlign.CENTER)
          .fontColor(this.selectedIndex === index ? '#e6000000' : '#99000000')
          .fontSize(14)
          .fontWeight(this.selectedIndex === index ? 500 : 400)
          .lineHeight(40)
          .backgroundColor(this.selectedIndex === index ? Color.White : '#00000000')
          .borderRadius('50vp');
      }
      .backgroundColor('#0d000000')
      .borderRadius({
        topLeft: index === 0 ? 50 : 0,
        bottomLeft: index === 0 ? 50 : 0,
        topRight: index === 2 ? 50 : 0,
        bottomRight: index === 2 ? 50 : 0
      })
      .padding({
        top: 2,
        bottom: 2,
        left: 2,
        right: 2
      });
    }
    .onClick(() => {
      this.controller.changeIndex(index);
      this.selectedIndex = index;
    });
  }

  build() {
    Column() {
      Row({ space: 10 }) {
        Scroll() {
          Row() {
            ForEach(this.tabName, (item: string, index: number) => {
              this.tabBuilder(index, item);
            });
          }
          .justifyContent(FlexAlign.Start);
        }
        .layoutWeight(1)
        .scrollable(ScrollDirection.Horizontal)
        .scrollBar(BarState.Off);

        Image($r('sys.media.ohos_ic_public_more'))<em> // 开发者可根据需求更换其它图片资源</em>
          .width(32)
          .height(32)
          .onClick(() => {
            try {
              this.getUIContext().getPromptAction().showToast({
                message: '触发开发者自定义事件',
                duration: 2000,
                showMode: promptAction.ToastShowMode.TOP_MOST,
                bottom: 85
              });
            } catch (error) {
              let message = (error as BusinessError).message;
              let code = (error as BusinessError).code;
              console.error(`showToast args error code is ${code}, message is ${message}.`);
            }
          });
      }
      .margin({ top: 16 })
      .padding({ left: 10, right: 10 })
      .alignItems(VerticalAlign.Center)
      .width('100%')
      .height(40);

      Tabs({ barPosition: BarPosition.Start, controller: this.controller }) {
        ForEach(this.tabName, () => {
          TabContent() {
            Column()
              .width('100%')
              .height('100%');
          };
        });
      }
      .margin({ top: 2 })
      .width('100%')
      .barHeight(0)
      .animationDuration(100)
      .onChange((index: number) => {
        this.selectedIndex = index;
      });
    }
    .height('100%');
  }
}
```
 实现效果如下：

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/b3/v3/_sLOUGm4TkSq63scCQ4aQw/zh-cn_image_0000002628567146.png?HW-CC-KV=V1&HW-CC-Date=20260911T072742Z&HW-CC-Expire=86400&HW-CC-Sign=C192A7BB32F23B79D5A40C959490B00341FEDF291DF078A2971401C89AC68356)
