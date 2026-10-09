# @ohos.multimodalInput.pointer (鼠标光标)

更新时间：2026-09-17 01:44:14

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/js-apis-pointer
**支持设备：** Phone | PC/2in1 | Tablet | TV

鼠标光标管理模块，用于查询和设置鼠标光标相关属性。

> [!NOTE]
> 本模块首批接口从API version 9开始支持。后续版本的新增接口，采用上角标单独标记接口的起始版本。



## 导入模块


**支持设备：** Phone | PC/2in1 | Tablet | TV

```text
import { pointer } from '@kit.InputKit';
import { BusinessError } from '@kit.BasicServicesKit';
```



## pointer.setPointerVisible


**支持设备：** Phone | PC/2in1 | Tablet | TV

setPointerVisible(visible: boolean, callback: AsyncCallback&lt;void&gt;): void

设置光标显示/隐藏状态，此状态作用于当前进程的所有窗口。光标在屏幕上的实际显示/隐藏效果还受渲染服务进程影响。使用callback异步回调。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer

**参数**：


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| visible | boolean | 是 | 当前窗口鼠标光标是否显示。true表示显示，false表示不显示。 |
| callback | AsyncCallback&lt;void&gt; | 是 | 回调函数。当设置鼠标光标显示状态成功，err为undefined，否则为错误对象。 |


**错误码**：

以下错误码的详细介绍请参见[通用错误码](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/errorcode-universal)。


| 错误码ID | 错误信息 |
| --- | --- |
| 401 | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types; 3. Parameter verification failed. |
| 801 | Capability not supported. 适用版本：18+ |


**示例**：

```text
import { pointer } from '@kit.InputKit';
import { BusinessError } from '@kit.BasicServicesKit';

@Entry
@Component
struct Index {
  build() {
    RelativeContainer() {
      Text()
        .onClick(() => {
          try {
            // 设置鼠标指针可见性
            pointer.setPointerVisible(true, (error: BusinessError) => {
              if (error) {
                console.error(`Failed to set pointer cursor visible, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
                return;
              }
              console.info(`Succeeded in setting pointer cursor visible.`);
            });
          } catch (error) {
            console.error(`Failed to set pointer cursor visible, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
          }
        });
    }
  }
}
```



## pointer.setPointerVisible


**支持设备：** Phone | PC/2in1 | Tablet | TV

setPointerVisible(visible: boolean): Promise&lt;void&gt;

设置光标显示/隐藏状态，此状态作用于当前进程的所有窗口。光标在屏幕上的实际显示/隐藏效果还受渲染服务进程影响。使用Promise异步回调。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer

**参数**：


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| visible | boolean | 是 | 当前窗口鼠标光标是否显示。true表示显示，false表示不显示。 |


**返回值**：


| 类型 | 说明 |
| --- | --- |
| Promise&lt;void&gt; | Promise对象，无返回结果。 |


**错误码**：

以下错误码的详细介绍请参见[通用错误码](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/errorcode-universal)。


| 错误码ID | 错误信息 |
| --- | --- |
| 401 | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types; 3. Parameter verification failed. |
| 801 | Capability not supported. 适用版本：18+ |


**示例**：

```text
import { pointer } from '@kit.InputKit';
import { BusinessError } from '@kit.BasicServicesKit';

@Entry
@Component
struct Index {
  build() {
    RelativeContainer() {
      Text()
        .onClick(() => {
          try {
            // 设置鼠标指针可见性
            pointer.setPointerVisible(false).then(() => {
              console.info(`Succeeded in setting pointer cursor visible.`);
            }).catch((error: BusinessError) => {
              console.error(`Failed to set pointer cursor, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
            })
          } catch (error) {
            console.error(`Failed to set pointer cursor, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
          }
        })
    }
  }
}
```



## pointer.setPointerVisibleSync10+


**支持设备：** Phone | PC/2in1 | Tablet | TV

setPointerVisibleSync(visible: boolean): void

设置光标显示/隐藏状态，此状态作用于当前进程的所有窗口。光标在屏幕上的实际显示/隐藏效果还受渲染服务进程影响。函数调用方式为同步方式。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer

**参数**：


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| visible | boolean | 是 | 当前窗口鼠标光标是否显示。true表示显示，false表示不显示。 |


**错误码**：

以下错误码的详细介绍请参见[通用错误码](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/errorcode-universal)。


| 错误码ID | 错误信息 |
| --- | --- |
| 401 | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types; 3. Parameter verification failed. |


**示例**：

```text
import { pointer } from '@kit.InputKit';
import { BusinessError } from '@kit.BasicServicesKit';

@Entry
@Component
struct Index {
  build() {
    RelativeContainer() {
      Text()
        .onClick(() => {
          try {
            // 同步设置鼠标指针可见性
            pointer.setPointerVisibleSync(false);
            console.info(`Succeeded in setting pointer cursor visible.`);
          } catch (error) {
            console.error(`Failed to set pointer cursor visible, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
          }
        })
    }
  }
}
```



## pointer.isPointerVisible


**支持设备：** Phone | PC/2in1 | Tablet | TV

isPointerVisible(callback: AsyncCallback&lt;boolean&gt;): void

获取当前窗口的显示/隐藏状态，此状态反映的是多模进程对此窗口所在进程的光标显示/隐藏状态，并非真实的光标显示/隐藏情况，光标是否正确显示/隐藏还受渲染服务进程影响，使用callback异步回调。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer

**参数**：


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| callback | AsyncCallback&lt;boolean&gt; | 是 | 回调函数。当获取鼠标光标显示状态成功，err为undefined，data为鼠标光标状态（true为显示，false为隐藏）；否则为错误对象。 |


**错误码**：

以下错误码的详细介绍请参见[通用错误码](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/errorcode-universal)。


| 错误码ID | 错误信息 |
| --- | --- |
| 401 | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types; 3. Parameter verification failed. |


**示例**：

```json
import { pointer } from '@kit.InputKit';
import { BusinessError } from '@kit.BasicServicesKit';

@Entry
@Component
struct Index {
  build() {
    RelativeContainer() {
      Text()
        .onClick(() => {
          try {
            // 查询鼠标指针是否可见
            pointer.isPointerVisible((error: BusinessError, visible: boolean) => {
              if (error) {
                console.error(`Failed to get pointer visible, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
                return;
              }
              console.info(`Succeeded in getting pointer visible, visible: ${JSON.stringify(visible)}.`);
            });
          } catch (error) {
            console.error(`Failed to get pointer visible, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
          }
        })
    }
  }
}
```



## pointer.isPointerVisible


**支持设备：** Phone | PC/2in1 | Tablet | TV

isPointerVisible(): Promise&lt;boolean&gt;

获取当前窗口的显示/隐藏状态，此状态反映的是多模进程对此窗口所在进程的光标显示/隐藏状态，并非真实的光标显示/隐藏情况，光标是否正确显示/隐藏还受渲染服务进程影响，使用Promise异步回调。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer

**返回值**：


| 类型 | 说明 |
| --- | --- |
| Promise&lt;boolean&gt; | Promise对象。返回true表示鼠标光标为显示状态；返回false表示鼠标光标为隐藏状态。 |


**示例**：

```json
import { pointer } from '@kit.InputKit';
import { BusinessError } from '@kit.BasicServicesKit';

@Entry
@Component
struct Index {
  build() {
    RelativeContainer() {
      Text()
        .onClick(() => {
          try {
            // 查询鼠标指针是否可见
            pointer.isPointerVisible().then((visible: boolean) => {
              console.info(`Succeeded in getting pointer visible, visible: ${JSON.stringify(visible)}.`);
            }).catch((error: BusinessError) => {
              console.error(`Failed to get pointer, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
            })
          } catch (error) {
            console.error(`Failed to get pointer visible, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
          }
        })
    }
  }
}
```



## pointer.isPointerVisibleSync10+


**支持设备：** Phone | PC/2in1 | Tablet | TV

isPointerVisibleSync(): boolean

获取当前窗口的显示/隐藏状态，此状态反映的是多模进程对此窗口所在进程的光标显示/隐藏状态，并非真实的光标显示/隐藏情况，光标是否正确显示/隐藏还受渲染服务进程影响，函数调用使用同步方式。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer

**返回值**：


| 类型 | 说明 |
| --- | --- |
| boolean | 返回鼠标光标显示或隐藏状态。true代表显示状态，false代表隐藏状态。 |


**示例**：

```json
import { pointer } from '@kit.InputKit';
import { BusinessError } from '@kit.BasicServicesKit';

@Entry
@Component
struct Index {
  build() {
    RelativeContainer() {
      Text()
        .onClick(() => {
          try {
            let visible: boolean = pointer.isPointerVisibleSync();
            console.info(`Succeeded in getting pointer visible, visible: ${JSON.stringify(visible)}.`);
          } catch (error) {
            console.error(`Failed to get pointer visible, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
          }
        })
    }
  }
}
```



## pointer.getPointerStyle


**支持设备：** Phone | PC/2in1 | Tablet | TV

getPointerStyle(windowId: number, callback: AsyncCallback&lt;PointerStyle&gt;): void

获取指定窗口的鼠标样式类型，此接口仅支持获取本应用进程内窗口的鼠标样式类型，使用callback异步回调。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer

**参数**：


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| windowId | number | 是 | 窗口ID。取值范围为大于等于-1的整数，取值为-1时表示全局窗口。 窗口ID合法并且对应窗口存在时，返回窗口的鼠标光标样式。 窗口ID合法但窗口不存在时，默认返回全局鼠标光标样式。 如果通过setPointerStyle接口为不存在的窗口设置了鼠标光标样式，使用本接口可以正常获取到该光标样式。 |
| callback | AsyncCallback&lt;PointerStyle&gt; | 是 | 回调函数。当获取鼠标样式类型成功时，err为undefined，data为鼠标样式类型；否则为错误对象。在特定场景（在设置自定义光标样式的窗口上获取样式）下返回DEVELOPER_DEFINED_ICON。 |


**错误码**：

以下错误码的详细介绍请参见[通用错误码](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/errorcode-universal)。


| 错误码ID | 错误信息 |
| --- | --- |
| 401 | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types; 3. Parameter verification failed. |


**示例**：

```json
import { pointer } from '@kit.InputKit';
import { BusinessError } from '@kit.BasicServicesKit';
import { window } from '@kit.ArkUI';

@Entry
@Component
struct Index {
  build() {
    RelativeContainer() {
      Text()
        .onClick(() => {
          // 获取应用内最近一个窗口
          window.getLastWindow(this.getUIContext().getHostContext(), (error: BusinessError, win: window.Window) => {
            if (error) {
              console.error(`Failed to obtain the top window, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
              return;
            }
            let windowId = win.getWindowProperties().id;
            if (windowId < 0) {
              console.info(`Invalid windowId.`);
              return;
            }
            try {
              // 获取鼠标指针样式
              pointer.getPointerStyle(windowId, (error: BusinessError, style: pointer.PointerStyle) => {
                if (error) {
                  console.error(`Failed to get pointer style, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
                  return;
                }
                console.info(`Succeeded in getting pointer style, style: ${JSON.stringify(style)}.`);
              });
            } catch (error) {
              console.error(`Failed to get pointer style, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
            }
          });
        })
    }
  }
}
```



## pointer.getPointerStyle


**支持设备：** Phone | PC/2in1 | Tablet | TV

getPointerStyle(windowId: number): Promise&lt;PointerStyle&gt;

获取鼠标样式类型，此接口仅支持获取本应用进程内窗口的鼠标样式类型，使用Promise异步回调。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer

**参数**：


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| windowId | number | 是 | 窗口ID。取值范围为大于等于-1的整数，取值为-1时表示全局窗口。 窗口ID合法并且对应窗口存在时，返回窗口的鼠标光标样式。 窗口ID合法但窗口不存在时，默认返回全局鼠标光标样式。 如果通过setPointerStyle接口为不存在的窗口设置了鼠标光标样式，使用本接口可以正常获取到该光标样式。 |


**返回值**：


| 类型 | 说明 |
| --- | --- |
| Promise&lt;PointerStyle&gt; | Promise对象，返回鼠标样式类型。 |


**错误码**：

以下错误码的详细介绍请参见[通用错误码](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/errorcode-universal)。


| 错误码ID | 错误信息 |
| --- | --- |
| 401 | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types; 3. Parameter verification failed. |


**示例**：

```json
import { pointer } from '@kit.InputKit';
import { BusinessError } from '@kit.BasicServicesKit';
import { window } from '@kit.ArkUI';

@Entry
@Component
struct Index {
  build() {
    RelativeContainer() {
      Text()
        .onClick(() => {
          // 获取应用内最近一个窗口
          window.getLastWindow(this.getUIContext().getHostContext(), (error: BusinessError, win: window.Window) => {
            if (error.code) {
              console.error(`Failed to obtain the top window, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
              return;
            }
            let windowId = win.getWindowProperties().id;
            if (windowId < 0) {
              console.info(`Invalid windowId.`);
              return;
            }
            try {
              // 获取鼠标指针样式
              pointer.getPointerStyle(windowId).then((style: pointer.PointerStyle) => {
                console.info(`Succeeded in getting pointer style, style: ${JSON.stringify(style)}.`);
              }).catch((error: BusinessError) => {
                console.error(`Failed to get pointer style, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
              });
            } catch (error) {
              console.error(`Failed to get pointer style, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
            }
          });
        })
    }
  }
}
```



## pointer.getPointerStyleSync10+


**支持设备：** Phone | PC/2in1 | Tablet | TV

getPointerStyleSync(windowId: number): PointerStyle

查询指定窗口的鼠标样式类型，如向东箭头、向西箭头、向南箭头、向北箭头等。此接口仅支持获取本应用进程内窗口的鼠标样式类型。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer

**参数**：


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| windowId | number | 是 | 窗口ID。取值范围为大于等于-1的整数，取值为-1时表示全局窗口。 窗口ID合法并且对应窗口存在时，返回窗口的鼠标光标样式。 窗口ID合法但窗口不存在时，默认返回全局鼠标光标样式。 如果通过setPointerStyleSync接口为不存在的窗口设置了鼠标光标样式，使用本接口可以正常获取到该光标样式。 |


**返回值**：


| 类型 | 说明 |
| --- | --- |
| PointerStyle | 返回鼠标样式类型。 |


**错误码**：

以下错误码的详细介绍请参见[通用错误码](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/errorcode-universal)。


| 错误码ID | 错误信息 |
| --- | --- |
| 401 | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types; 3. Parameter verification failed. |


**示例**：

```json
import { pointer } from '@kit.InputKit';
import { BusinessError } from '@kit.BasicServicesKit';

@Entry
@Component
struct Index {
  build() {
    RelativeContainer() {
      Text()
        .onClick(() => {
          let windowId = -1;
          try {
            let style: pointer.PointerStyle = pointer.getPointerStyleSync(windowId);
            console.info(`Succeeded in getting pointer style, style: ${JSON.stringify(style)}.`);
          } catch (error) {
            console.error(`Failed to get pointer style, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
          }
        })
    }
  }
}
```



## pointer.setPointerStyle


**支持设备：** Phone | PC/2in1 | Tablet | TV

setPointerStyle(windowId: number, pointerStyle: PointerStyle, callback: AsyncCallback&lt;void&gt;): void

设置指定窗口的鼠标样式类型，此接口仅支持设置本应用进程内窗口的鼠标样式类型，如需通过UIExtensionAbility进程设置宿主窗口的鼠标样式类型，请参阅[setCursor](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/arkts-apis-uicontext-cursorcontroller#setcursor12)，使用callback异步回调。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer

**参数**：


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| windowId | number | 是 | 窗口ID。取值范围为大于等于0的整数。 窗口ID合法并且对应窗口存在时，可以设置窗口的鼠标光标样式。 窗口ID合法但窗口不存在时，也可以设置鼠标光标样式。 设置结果可通过getPointerStyle获取。 |
| pointerStyle | PointerStyle | 是 | 鼠标样式。 不能传入DEVELOPER_DEFINED_ICON作为参数。 |
| callback | AsyncCallback&lt;void&gt; | 是 | 回调函数。当设置鼠标样式类型成功，err为undefined，否则为错误对象。 |


**错误码**：

以下错误码的详细介绍请参见[通用错误码](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/errorcode-universal)。


| 错误码ID | 错误信息 |
| --- | --- |
| 401 | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types; 3. Parameter verification failed. |


**示例**：

```text
import { pointer } from '@kit.InputKit';
import { BusinessError } from '@kit.BasicServicesKit';
import { window } from '@kit.ArkUI';

@Entry
@Component
struct Index {
  build() {
    RelativeContainer() {
      Text()
        .onClick(() => {
          // 获取应用内最近一个窗口
          window.getLastWindow(this.getUIContext().getHostContext(), (error: BusinessError, win: window.Window) => {
            if (error.code) {
              console.error(`Failed to obtain the top window, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
              return;
            }
            let windowId = win.getWindowProperties().id;
            if (windowId < 0) {
              console.info(`Invalid windowId.`);
              return;
            }
            try {
              // 设置鼠标指针样式
              pointer.setPointerStyle(windowId, pointer.PointerStyle.CROSS, error => {
                console.info(`Succeeded in setting pointer style.`);
              });
            } catch (error) {
              console.error(`Failed to set pointer style, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
            }
          });
        })
    }
  }
}
```



## pointer.setPointerStyle


**支持设备：** Phone | PC/2in1 | Tablet | TV

setPointerStyle(windowId: number, pointerStyle: PointerStyle): Promise&lt;void&gt;

设置指定窗口的鼠标样式类型，此接口仅支持设置本应用进程内窗口的鼠标样式类型，如需通过UIExtensionAbility进程设置宿主窗口的鼠标样式类型，请参阅[setCursor](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/arkts-apis-uicontext-cursorcontroller#setcursor12)，使用Promise异步回调。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer

**参数**：


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| windowId | number | 是 | 窗口ID。取值范围为大于等于0的整数。 窗口ID合法并且对应窗口存在时，可以设置窗口的鼠标光标样式。 窗口ID合法但窗口不存在时，也可以设置鼠标光标样式。 设置结果可通过getPointerStyle获取。 |
| pointerStyle | PointerStyle | 是 | 鼠标样式。不能传入DEVELOPER_DEFINED_ICON作为参数。 |


**返回值**：


| 类型 | 说明 |
| --- | --- |
| Promise&lt;void&gt; | Promise对象，无返回结果。 |


**错误码**：

以下错误码的详细介绍请参见[通用错误码](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/errorcode-universal)。


| 错误码ID | 错误信息 |
| --- | --- |
| 401 | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types; 3. Parameter verification failed. |


**示例**：

```text
import { pointer } from '@kit.InputKit';
import { BusinessError } from '@kit.BasicServicesKit';
import { window } from '@kit.ArkUI';

@Entry
@Component
struct Index {
  build() {
    RelativeContainer() {
      Text()
        .onClick(() => {
          // 获取应用内最近一个窗口
          window.getLastWindow(this.getUIContext().getHostContext(), (error: BusinessError, win: window.Window) => {
            if (error.code) {
              console.error(`Failed to obtain the top window, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
              return;
            }
            let windowId = win.getWindowProperties().id;
            if (windowId < 0) {
              console.info(`Invalid windowId.`);
              return;
            }
            try {
              // 设置鼠标指针样式
              pointer.setPointerStyle(windowId, pointer.PointerStyle.CROSS).then(() => {
                console.info(`Succeeded in setting pointer style.`);
              }).catch((error: BusinessError) => {
                console.error(`Failed to set pointer style, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
              });
            } catch (error) {
              console.error(`Failed to set pointer style, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
            }
          });
        })
    }
  }
}
```



## pointer.setPointerStyleSync10+


**支持设备：** Phone | PC/2in1 | Tablet | TV

setPointerStyleSync(windowId: number, pointerStyle: PointerStyle): void

设置指定窗口的鼠标样式类型，使用同步方式返回结果。此接口仅支持设置本应用进程内窗口的鼠标样式类型，如需通过UIExtensionAbility进程设置宿主窗口的鼠标样式类型，请参阅[setCursor](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/arkts-apis-uicontext-cursorcontroller#setcursor12)。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer

**参数**：


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| windowId | number | 是 | 窗口ID。取值范围为大于等于0的整数。 窗口ID合法并且对应窗口存在时，可以设置窗口的鼠标光标样式。 窗口ID合法但窗口不存在时，也可以设置鼠标光标样式。 设置结果可通过getPointerStyleSync获取。 |
| pointerStyle | PointerStyle | 是 | 鼠标样式。不能传入DEVELOPER_DEFINED_ICON作为参数。 |


**错误码**：

以下错误码的详细介绍请参见[通用错误码](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/errorcode-universal)。


| 错误码ID | 错误信息 |
| --- | --- |
| 401 | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types; 3. Parameter verification failed. |


**示例**：

```text
import { pointer } from '@kit.InputKit';
import { BusinessError } from '@kit.BasicServicesKit';
import { window } from '@kit.ArkUI';

@Entry
@Component
struct Index {
  build() {
    RelativeContainer() {
      Text()
        .onClick(() => {
          // 获取应用内最近一个窗口
          window.getLastWindow(this.getUIContext().getHostContext(), (error: BusinessError, win: window.Window) => {
            if (error.code) {
              console.error(`Failed to obtain the top window, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
              return;
            }
            let windowId = win.getWindowProperties().id;
            if (windowId < 0) {
              console.info(`Invalid windowId.`);
              return;
            }
            try {
              // 同步设置鼠标指针样式
              pointer.setPointerStyleSync(windowId, pointer.PointerStyle.CROSS);
              console.info(`Succeeded in setting pointer style.`);
            } catch (error) {
              console.error(`Failed to set pointer style, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
            }
          });
        })
    }
  }
}
```



## PrimaryButton10+


**支持设备：** Phone | PC/2in1 | Tablet | TV

鼠标主键类型。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer


| 名称 | 值 | 说明 |
| --- | --- | --- |
| LEFT | 0 | 鼠标左键。 |
| RIGHT | 1 | 鼠标右键。 |




## RightClickType10+


**支持设备：** Phone | PC/2in1 | Tablet | TV

右键菜单的触发方式。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer


| 名称 | 值 | 说明 |
| --- | --- | --- |
| TOUCHPAD_RIGHT_BUTTON | 1 | 按压触控板右键区域。 |
| TOUCHPAD_LEFT_BUTTON | 2 | 按压触控板左键区域。 |
| TOUCHPAD_TWO_FINGER_TAP | 3 | 双指轻击或双指按压触控板。 |
| TOUCHPAD_TWO_FINGER_TAP_OR_RIGHT_BUTTON20+ | 4 | 双指轻击或双指按压触控板、或按压触控板右键区域。 |
| TOUCHPAD_TWO_FINGER_TAP_OR_LEFT_BUTTON20+ | 5 | 双指轻击或双指按压触控板、或按压触控板左键区域。 |




## PointerStyle


**支持设备：** Phone | PC/2in1 | Tablet | TV

鼠标光标样式类型。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer


| 名称 | 值 | 说明 | 图示 |
| --- | --- | --- | --- |
| DEFAULT | 0 | 默认 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/87/v3/9XK9Q4yaTpeS1g-5s3yjAw/zh-cn_image_0000002749495556.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=F300A5BD2504D3E87D015829C46DD4C2DF58473FE0DA3783A780F90F3B35AC9C) |
| EAST | 1 | 向东箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/44/v3/bkqLb6WDRyKesyZkPsO4rQ/zh-cn_image_0000002779094613.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=7EE5FEC35ECAFCA6FD7FDDAE86256B7C01BAF368319D41474B4E12DA3A834123) |
| WEST | 2 | 向西箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ed/v3/EEcJgtQoQY6M-Voqd17m9g/zh-cn_image_0000002778934759.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=C6BA8ED770FA45467596385852C26CAB51D3203CD51C5EB753E63EAEA43341A7) |
| SOUTH | 3 | 向南箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/c/v3/OQhH2ap-Rr6_NeHlUBaViA/zh-cn_image_0000002749335674.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=47ECF13091B2190F671A127CE77F037F57B60E6B813D2DB386763EEEC9EEE931) |
| NORTH | 4 | 向北箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d7/v3/0t7QnkueREechMIvDu6kDg/zh-cn_image_0000002749495558.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=430A67A75A67F32B3EECAB4EBC7E35FDFCA69C1D3B5495A3906772B678F8DA05) |
| WEST_EAST | 5 | 向西东箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/95/v3/6wWiWefVSMCbtZXblGTpSw/zh-cn_image_0000002779094615.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=5CC7F99670B43C8CE8F2BD7B94851A0BB3318119DDA02B3F7552695EB5D3262F) |
| NORTH_SOUTH | 6 | 向北南箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/77/v3/IzG3Ae1pRICpb0a69khsnA/zh-cn_image_0000002778934761.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=A6593B7350C219EABCCA5F522ABCE2579D28F85501DCAC50ABE0E281D3FC5611) |
| NORTH_EAST | 7 | 向东北箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/32/v3/h_Nluv_JQTKlCcWxe1PpaA/zh-cn_image_0000002749335676.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=267C426A38D604CBC843E2519FFCCED5EC16C388AFD328B741903F2B1C07970B) |
| NORTH_WEST | 8 | 向西北箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/2/v3/kn1NVoVCTUWmFw0kymULyg/zh-cn_image_0000002749495560.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=F841DAE5D2A4AD5DCAD85B8BEF954FA558D2E9A07C11398F291F1F452B2803C8) |
| SOUTH_EAST | 9 | 向东南箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/3e/v3/KcnR0bQrQ82Er2QiCkDweg/zh-cn_image_0000002779094617.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=805EA773B054711A5DA3CC73EC2E96A5CC7BC19B7C6CE0E2209F9ECCC12C848A) |
| SOUTH_WEST | 10 | 向西南箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/f8/v3/VIYtdIG9SFGGfycu3sItgw/zh-cn_image_0000002778934763.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=7D04C4978586B3616B7BD6F167A5EE5BA21EC8E095743DAD3C751436282DAB8F) |
| NORTH_EAST_SOUTH_WEST | 11 | 东北西南调整 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/2a/v3/wBCMdFuZS0yFXyatFPWAkg/zh-cn_image_0000002749335678.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=998B6CC3A2897E1F7096F2D149BBFEF71132BCA5A0EEE941FA7C2A3025680374) |
| NORTH_WEST_SOUTH_EAST | 12 | 西北东南调整 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/5/v3/ah4_rBDJSYaZKeHDXSiJkw/zh-cn_image_0000002749495562.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=5675CA2D14D366C14AEEB9F4E2B8BC32BDC40544A075DAAF5ABED9991C0D966A) |
| CROSS | 13 | 准确选择 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ec/v3/LkEaANpJTkSkK6LvVm2uuA/zh-cn_image_0000002779094619.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=389E1E4CCF255AE75AD8A9D6EBC7A0719F45378FF13D19DF0F167736DB3DF201) |
| CURSOR_COPY | 14 | 复制 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/f2/v3/8uPm5ziGTOiCtF5Zot6TKQ/zh-cn_image_0000002778934765.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=18E9ADFC7408D08059CB67B42B077D54AA71592110889C01E3B6A78C8509B626) |
| CURSOR_FORBID | 15 | 不可用 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/13/v3/5nBikA5PTLG27NPiUyd5gA/zh-cn_image_0000002749335680.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=CC82F994B49C8523DD0A45EF87ED7674BE98F298B666314946A0BD12F8DF4BB5) |
| COLOR_SUCKER | 16 | 取色器 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/5/v3/ENb9UykvSu-51HzlthntxA/zh-cn_image_0000002749495564.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=6EAD61A6DEE6DD232E6EB58C5532F1F9B5825C60AF7E16C168D222FCBCAE638D) |
| HAND_GRABBING | 17 | 并拢的手 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/62/v3/3XVyjH1OQvm13WZsfkXNdA/zh-cn_image_0000002779094621.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=00B6C00560F8DF46DAF81018236B53F32DF46288196F8824A1DE1269FE4BCB70) |
| HAND_OPEN | 18 | 张开的手 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/7f/v3/yYyq7WyWRISQoQFdhEE-BQ/zh-cn_image_0000002778934767.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=98A8A5071481B3FA1343FEBA7E7E486E27B7B5CACC78315BFC1415FAB7EC2A43) |
| HAND_POINTING | 19 | 手形指针 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/58/v3/mg6aCzMeTfWPhvvcJbC9gw/zh-cn_image_0000002749335682.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=2824F351CDC264A9F8E5874ED39FB2432F5A373B163C4B97FBD7062845DC4468) |
| HELP | 20 | 帮助选择 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/80/v3/_S4O9RL-SKG5RaQewIEW7A/zh-cn_image_0000002749495566.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=D393F9FC0FE10793397D7EA8B0F95FC480F61E39D2CCB735137A7208CE7A0B1E) |
| MOVE | 21 | 移动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/9c/v3/pnXJg7hERxinSmnhXmvRbQ/zh-cn_image_0000002779094623.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=967C2B3AE1E98A3F329BD507D25155A1135D46F51B1D589FF27730569317F171) |
| RESIZE_LEFT_RIGHT | 22 | 内部左右调整 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a3/v3/bJl_oMYARX-i0vW6FNiCxQ/zh-cn_image_0000002778934769.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=CAD4A515C50A9DA906B10B653D9C7CB26CC8230DD6B6A8F18BC5B1A2CF6BB619) |
| RESIZE_UP_DOWN | 23 | 内部上下调整 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/1e/v3/gxohezspRAmvQ4lfo5n3Uw/zh-cn_image_0000002749335684.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=3A0BA4E71CDAC7DB0E0AFC3E90DD02279C9A9E7460F921DC6341F1004D7BEA22) |
| SCREENSHOT_CHOOSE | 24 | 截图十字准星 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/33/v3/BV1mIQIYQnSK0c5WJ5n5Hw/zh-cn_image_0000002749495568.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=482D148D23E9BC747663069245AAB649849E2BF645D3ADCB06C5E7EFE76D0A08) |
| SCREENSHOT_CURSOR | 25 | 截图 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/8a/v3/x2Ho4bcbQnyOElCxW95b3Q/zh-cn_image_0000002779094625.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=7E43F5775CF252A3276456E1E476D80D0A682EB9DA0939844CDA502CE8A3425B) |
| TEXT_CURSOR | 26 | 文本选择 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/52/v3/nCVzTOFCTtWDEFhLeGUj9Q/zh-cn_image_0000002778934771.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=4BEDA6CE71D6453C83D700B5C470ECDFCD21AABFDF69EB7B7110EA73B3D40DEB) |
| ZOOM_IN | 27 | 放大 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/88/v3/3RDjYpUuRwW8HpnCOK-mjw/zh-cn_image_0000002749335686.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=2275A2C4BFD71D3A81381CD077450C522310B964212D7B112017C4B6F430F309) |
| ZOOM_OUT | 28 | 缩小 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/32/v3/_FwI14v9QRuVILoGak4AHg/zh-cn_image_0000002749495570.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=0EA7EF115D439CA26C7DA9101D37F799CC17372416641A5C3564D870E4ECBAD5) |
| MIDDLE_BTN_EAST | 29 | 向东滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/85/v3/Ic6jUteLT4q5KfsbpNPFbQ/zh-cn_image_0000002779094627.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=8380319C559F097000A1DE5BE6BF3938AD2799605B67DBE1B2B1C841A222DF8B) |
| MIDDLE_BTN_WEST | 30 | 向西滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/df/v3/coN7qq5ETQ-y0_-lm2T5TQ/zh-cn_image_0000002778934773.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=BC4DB9D6D64500F324F506AAAED6163C00503D84E9E8FBF25FAAC9CD5D4734B4) |
| MIDDLE_BTN_SOUTH | 31 | 向南滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/95/v3/Z8MFDjb_TxaaalcI7CaTpw/zh-cn_image_0000002749335688.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=217BFCF3EE68BC6A401A3DA1DD015F9A450ED21761AD2A5B30CF5BBBD7E1CD68) |
| MIDDLE_BTN_NORTH | 32 | 向北滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/46/v3/gkBPRTvnQmemgHRAzEBNRA/zh-cn_image_0000002749495572.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=2AF260848F57CE6B82A6BB900BF69847E5D9A46FD0759EB9045E62538209D1DA) |
| MIDDLE_BTN_NORTH_SOUTH | 33 | 向南北滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/85/v3/Qh7DDPsAQSe2AZKjHR2i2Q/zh-cn_image_0000002779094629.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=DB623F9C77E4D312C19B4D408E502E6B9E94A680053BDCDB6FC85313B560C2CD) |
| MIDDLE_BTN_NORTH_EAST | 34 | 向东北滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/6d/v3/p5v9SDH6QR-5FS8qrMovbw/zh-cn_image_0000002778934775.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=ED80E5B651270EBDB4BB7223CEEE5EA794BD118E7409E5D21701FFA9C6E3779F) |
| MIDDLE_BTN_NORTH_WEST | 35 | 向西北滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/84/v3/uXMtg1FzStqEzQRF5uF2QA/zh-cn_image_0000002749335690.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=14BA060733F0D80462A0276424C06C648EA748DB50A79F31991AF254F1BBF6B0) |
| MIDDLE_BTN_SOUTH_EAST | 36 | 向东南滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/8e/v3/AiSUpjfFQXOUmuVK03j8Xg/zh-cn_image_0000002749495574.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=4DAFB79A07C0EF111A6968926267BA68BD021F29FCC3211EC199D48530FB5744) |
| MIDDLE_BTN_SOUTH_WEST | 37 | 向西南滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/50/v3/js32CYUxTgq5xknhpLWj5Q/zh-cn_image_0000002779094631.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=728D572F720B0242D9FAB0AF45D6589899B3F21FB63A7D779FC222C3663230B9) |
| MIDDLE_BTN_NORTH_SOUTH_WEST_EAST | 38 | 四向锥形移动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/31/v3/rElFAkJCTHSzVYy3FLbYuA/zh-cn_image_0000002778934777.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=C3766D920770A46DEB628A6C72A72DC3730FCF155194019F63F2C1D29DA536FD) |
| HORIZONTAL_TEXT_CURSOR10+ | 39 | 水平文本选择 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/1d/v3/iO2NlAIiSKWBAVFo2TM89Q/zh-cn_image_0000002749335692.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=CC4C2D61B8D7E667EB3B06EDADCDDA97D97F53B19C641235646FE5E79B7B4ADF) |
| CURSOR_CROSS10+ | 40 | 十字光标 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/6b/v3/v6vlsJd6Q8Wz8yu2aiGdrQ/zh-cn_image_0000002749495576.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=895FCF9EF7E9137595A1CB60ADB80C566508272B32939DCA09A5A39A8F303926) |
| CURSOR_CIRCLE10+ | 41 | 圆形光标 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/89/v3/5kX4Tez0TmGN9Zk6qH9GRQ/zh-cn_image_0000002779094633.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=6E951F731967768638AA31E2FEB85198A6BD8667D452D167AC983FFD07CB4409) |
| LOADING10+ | 42 | 正在载入动画光标 元服务API： 从API version 12开始，该接口支持在元服务中使用。 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/80/v3/32TPI6WbQSybhQfvJtQqrQ/zh-cn_image_0000002778934779.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=E657B6CDF1396D8E2A1D002EB61DEDEAC15CC117032E726C7874D86D65F39A5F) |
| RUNNING10+ | 43 | 后台运行中动画光标 元服务API： 从API version 12开始，该接口支持在元服务中使用。 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/8a/v3/zDR70fL-Rtm88Y-jdTaz7g/zh-cn_image_0000002749335694.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=C2831A056839C8C29CC5911F7EAF237410215290546CA1F2D6DB55FCD6654E69) |
| MIDDLE_BTN_EAST_WEST18+ | 44 | 向东西滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/82/v3/T0J9vP3TT3miciFaUpPDvg/zh-cn_image_0000002749495578.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=46F919B06C6F0ADC43FE3525710B56AD3A3E7CE58E30B64D0E020B46707C3792) |
| RUNNING_LEFT22+ | 45 | 后台运行中动画光标（拓展1） | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/5a/v3/lhfAh9HwRiK1Xz4Ielmx4Q/zh-cn_image_0000002779094635.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=0F1F341CAB75D27176161B87DC9ADEB3C990131CE0711F74EE24E9D15919E437) |
| RUNNING_RIGHT22+ | 46 | 后台运行中动画光标（拓展2） | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/1d/v3/zv4bGiFRSoCZP0CpVeIogw/zh-cn_image_0000002778934781.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=906B4E4F317624C78ABC5A9CDBB577E403D451534587BC6D53E79912EE2E0EC7) |
| AECH_DEVELOPER_DEFINED_ICON22+ | 47 | 圆形自定义光标 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/1e/v3/oKiIwSMVQg-znJXWaLTf5w/zh-cn_image_0000002749335696.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=4DE83EAAA36325EF47B7D0B905F3459A5C64AEB48A24F3357BD06C4D5D37D8B8) |
| SCREENRECORDER_CURSOR20+ | 48 | 录屏光标 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a4/v3/K7_yEE3sSriISD0jD44uTw/zh-cn_image_0000002749495580.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=153741643EFE19603D0F9F78A0C68C138DE77934558CCAF7DEEA776D88F6B02E) |
| LASER_CURSOR22+ | 49 | 悬浮光标。手写笔进入空鼠模式时使用该光标，无法直接设置。 空鼠模式支持通过手写笔在空中转动来控制屏幕上虚拟光标的移动，并借助笔身按键实现上下翻页功能，用于演示PPT、隔空操作等场景。 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/38/v3/rT6D-UWaToC9BbyIYneuWg/zh-cn_image_0000002779094637.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=2B7219C15A1D3422927BF1A5D928830DC6708A2ED2D8B0FB419EA049E8939D0A) |
| LASER_CURSOR_DOT22+ | 50 | 点击光标。手写笔进入空鼠模式时使用该光标，无法直接设置。 空鼠模式支持通过手写笔在空中转动来控制屏幕上虚拟光标的移动，并借助笔身按键实现上下翻页功能，用于演示PPT、隔空操作等场景。 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/2/v3/MxLLUwdcRge1ApvEBYxZig/zh-cn_image_0000002778934783.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=23A46652CF71B3F7A86FA03416D843FA4E9B4756AEE533A38C85A84B771C6546) |
| LASER_CURSOR_DOT_RED22+ | 51 | 激光笔光标。手写笔进入空鼠模式时使用该光标，无法直接设置。 空鼠模式支持通过手写笔在空中转动来控制屏幕上虚拟光标的移动，并借助笔身按键实现上下翻页功能，用于演示PPT、隔空操作等场景。 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/5f/v3/RD200hPWTxqII65l78FXDA/zh-cn_image_0000002749335698.png?HW-CC-KV=V1&HW-CC-Date=20261009T012950Z&HW-CC-Expire=86400&HW-CC-Sign=D451035567E73F57520682AA529A2E7F85ED04B2F4946ABBAF62FE0F5326BE0F) |
| DEVELOPER_DEFINED_ICON22+ | -100 | 自定义光标，开发者可使用setCustomCursor设置自定义光标，不支持使用setPointerStyle直接设置。 | 自定义光标样式，通过接口设置。该参数用于getPointerStyle在特定场景（在设置自定义光标样式的窗口上获取样式）下返回数据，不能作为setCustomCursor、setPointerStyle接口入参使用。 |




## pointer.setCustomCursor11+


**支持设备：** Phone | PC/2in1 | Tablet | TV

setCustomCursor(windowId: number, pixelMap: image.PixelMap, focusX?: number, focusY?: number): Promise&lt;void&gt;

设置指定窗口的自定义光标样式，此接口仅支持设置本应用进程内窗口的自定义光标样式，如需通过UIExtensionAbility进程设置宿主窗口的自定义光标样式，请参阅[setCustomCursor](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/arkts-apis-uicontext-cursorcontroller#setcustomcursor)，使用Promise异步回调。

应用窗口布局改变、热区切换、页面跳转、光标移出再回到窗口、光标在窗口不同区域移动，以上场景可能导致光标切换回系统样式，需要开发者重新设置光标样式。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer

**参数**：


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| windowId | number | 是 | 窗口ID。取值为大于0的整数。 |
| pixelMap | image.PixelMap | 是 | 自定义光标资源。 |
| focusX | number | 否 | 自定义光标焦点x，取值范围：大于等于0，默认为0，单位为像素（px）。 |
| focusY | number | 否 | 自定义光标焦点y，取值范围：大于等于0，默认为0，单位为像素（px）。 |


**返回值**：


| 类型 | 说明 |
| --- | --- |
| Promise&lt;void&gt; | Promise对象，无返回结果。 |


**错误码**：

以下错误码的详细介绍请参见[通用错误码](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/errorcode-universal)。


| 错误码ID | 错误信息 |
| --- | --- |
| 401 | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types; 3. Parameter verification failed. |


**示例**：

```text
import { pointer } from '@kit.InputKit';
import { image } from '@kit.ImageKit';
import { BusinessError } from '@kit.BasicServicesKit';
import { window } from '@kit.ArkUI';

@Entry
@Component
struct Index {
  build() {
    RelativeContainer() {
      Text()
        .onClick(() => {
          // app_icon为示例资源，请开发者根据实际需求配置资源文件。
          this.getUIContext()?.getHostContext()?.resourceManager.getMediaContent(
            $r('app.media.app_icon').id, (error: BusinessError, svgFileData: Uint8Array) => {
            const svgBuffer: ArrayBuffer = svgFileData.buffer.slice(0);
            let svgImageSource: image.ImageSource = image.createImageSource(svgBuffer);
            let svgDecodingOptions: image.DecodingOptions = { desiredSize: { width: 50, height: 50 } };
            // 创建PixelMap
            svgImageSource.createPixelMap(svgDecodingOptions).then((pixelMap) => {
              window.getLastWindow(this.getUIContext().getHostContext(), (error: BusinessError, win: window.Window) => {
                let windowId = win.getWindowProperties().id;
                try {
                  pointer.setCustomCursor(windowId, pixelMap).then(() => {
                    console.info(`Succeeded in setting custom cursor.`);
                  });
                } catch (error) {
                  console.error(`Failed to set custom cursor, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
                }
              });
            }).catch((error: BusinessError) => {
                console.error(`Failed to create pixel map promise, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
              });
          });
        })
    }
  }
}
```



## CustomCursor15+


**支持设备：** Phone | PC/2in1 | Tablet | TV

自定义光标资源。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer


| 名称 | 类型 | 只读 | 可选 | 说明 |
| --- | --- | --- | --- | --- |
| pixelMap | image.PixelMap | 否 | 否 | 自定义光标。最小限制为资源图本身的最小限制。最大限制为256 x 256px。 |
| focusX | number | 否 | 是 | 自定义光标焦点的水平坐标。该坐标受自定义光标大小的限制。最小值为0，最大值为资源图的宽度最大值，该参数缺省时默认为0，单位为像素（px）。 |
| focusY | number | 否 | 是 | 自定义光标焦点的垂直坐标。该坐标受自定义光标大小的限制。最小值为0，最大值为资源图的高度最大值，该参数缺省时默认为0，单位为像素（px）。 |




## CursorConfig15+


**支持设备：** Phone | PC/2in1 | Tablet | TV

自定义光标配置。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer


| 名称 | 类型 | 只读 | 可选 | 说明 |
| --- | --- | --- | --- | --- |
| followSystem | boolean | 否 | 否 | 是否根据系统设置调整光标大小。false表示使用自定义光标样式大小，true表示根据系统设置调整光标大小，可调整范围为：[光标资源图大小, 256×256]。 |




## pointer.setCustomCursor15+


**支持设备：** Phone | PC/2in1 | Tablet | TV

setCustomCursor(windowId: number, cursor: CustomCursor, config: CursorConfig): Promise&lt;void&gt;

设置指定窗口的自定义光标样式，此接口仅支持设置本应用进程内窗口的自定义光标样式，如需通过UIExtensionAbility进程设置宿主窗口的自定义光标样式，请参阅[setCustomCursor](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/arkts-apis-uicontext-cursorcontroller#setcustomcursor)，使用Promise异步回调。

应用窗口布局改变、热区切换、页面跳转、光标移出再回到窗口、光标在窗口不同区域移动，以上场景可能导致光标切换回系统样式，需要开发者重新设置光标样式。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer

**参数**：


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| windowId | number | 是 | 窗口ID。取值为大于0的整数。 |
| cursor | CustomCursor | 是 | 自定义光标资源。 |
| config | CursorConfig | 是 | 自定义光标配置，用于配置是否根据系统设置调整光标大小。如果CursorConfig中followSystem设置为true，则光标大小的可调整范围为：[光标资源图大小, 256×256]。 |


**返回值**：


| 类型 | 说明 |
| --- | --- |
| Promise&lt;void&gt; | Promise对象，无返回结果。 |


**错误码**：

以下错误码的详细介绍请参见[通用错误码](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/errorcode-universal)和[鼠标光标错误码](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/errorcode-pointer)。


| 错误码ID | 错误信息 |
| --- | --- |
| 401 | Parameter error. Possible causes: 1. Abnormal windowId parameter passed in. 2. Abnormal pixelMap parameter passed in; 3. Abnormal focusX parameter passed in.4. Abnormal focusY parameter passed in. |
| 26500001 | Invalid windowId. Possible causes: The window id does not belong to the current process. |


**示例**：

```text
import { pointer } from '@kit.InputKit';
import { image } from '@kit.ImageKit';
import { BusinessError } from '@kit.BasicServicesKit';
import { window } from '@kit.ArkUI';

@Entry
@Component
struct Index {
  build() {
    RelativeContainer() {
      Text()
        .onClick(() => {
          // app_icon为示例资源，请开发者根据实际需求配置资源文件。
          this.getUIContext()?.getHostContext()?.resourceManager.getMediaContent(
            $r('app.media.app_icon').id, (error: BusinessError, svgFileData: Uint8Array) => {
            const svgBuffer: ArrayBuffer = svgFileData.buffer.slice(0);
            let svgImageSource: image.ImageSource = image.createImageSource(svgBuffer);
            let svgDecodingOptions: image.DecodingOptions = { desiredSize: { width: 50, height: 50 } };
            // 创建PixelMap
            svgImageSource.createPixelMap(svgDecodingOptions).then((pixelMap) => {
              // 获取应用内最近一个窗口
              window.getLastWindow(this.getUIContext().getHostContext(), (error: BusinessError, win: window.Window) => {
                let windowId = win.getWindowProperties().id;
                try {
                  // 设置自定义光标
                  pointer.setCustomCursor(windowId, { pixelMap: pixelMap, focusX: 25, focusY: 25 },
                    { followSystem: false }).then(() => {
                    console.info(`Succeeded in setting custom cursor.`);
                  });
                } catch (error) {
                  console.error(`Failed to set custom cursor, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
                }
              });
            }).catch((error: BusinessError) => {
                console.error(`Failed to create pixel map promise, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
              });
          });
        })
    }
  }
}
```



## pointer.setCustomCursorSync11+


**支持设备：** Phone | PC/2in1 | Tablet | TV

setCustomCursorSync(windowId: number, pixelMap: image.PixelMap, focusX?: number, focusY?: number): void

设置指定窗口的自定义光标样式，使用同步方式进行设置。此接口仅支持设置本应用进程内窗口的自定义光标样式，如需通过UIExtensionAbility进程设置宿主窗口的自定义光标样式，请参阅[setCustomCursor](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/arkts-apis-uicontext-cursorcontroller#setcustomcursor)。

应用窗口布局改变、热区切换、页面跳转、光标移出再回到窗口、光标在窗口不同区域移动，以上场景可能导致光标切换回系统样式，需要开发者重新设置光标样式。

**系统能力**：SystemCapability.MultimodalInput.Input.Pointer

**参数**：


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| windowId | number | 是 | 窗口ID。取值为大于0的整数。 |
| pixelMap | image.PixelMap | 是 | 自定义光标资源。 |
| focusX | number | 否 | 自定义光标焦点x，取值范围：大于等于0，默认为0，单位为像素（px）。 |
| focusY | number | 否 | 自定义光标焦点y，取值范围：大于等于0，默认为0，单位为像素（px）。 |


**错误码**：

以下错误码的详细介绍请参见[通用错误码](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/errorcode-universal)。


| 错误码ID | 错误信息 |
| --- | --- |
| 401 | Parameter error. Possible causes: 1. Mandatory parameters are left unspecified; 2. Incorrect parameter types; 3. Parameter verification failed. |


**示例**：

```text
import { pointer } from '@kit.InputKit';
import { image } from '@kit.ImageKit';
import { BusinessError } from '@kit.BasicServicesKit';
import { window } from '@kit.ArkUI';

@Entry
@Component
struct Index {
  build() {
    RelativeContainer() {
      Text()
        .onClick(() => {
          // app_icon为示例资源，请开发者根据实际需求配置资源文件。
          this.getUIContext()?.getHostContext()?.resourceManager.getMediaContent(
            $r('app.media.app_icon').id, (error: BusinessError, svgFileData: Uint8Array) => {
            const svgBuffer = svgFileData.buffer;
            let svgImageSource: image.ImageSource = image.createImageSource(svgBuffer);
            // 光标图片宽高
            let svgDecodingOptions: image.DecodingOptions = { desiredSize: { width: 50, height: 50 } };
            // 创建PixelMap
            svgImageSource.createPixelMap(svgDecodingOptions).then((pixelMap) => {
              // 获取应用内最近一个窗口
              window.getLastWindow(this.getUIContext().getHostContext(), (error: BusinessError, win: window.Window) => {
                let windowId = win.getWindowProperties().id;
                try {
                  // 同步设置自定义光标
                  pointer.setCustomCursorSync(windowId, pixelMap, 25, 25);
                  console.info(`Succeeded in setting custom cursor sync.`);
                } catch (error) {
                  console.error(`Failed to set custom cursor sync, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
                }
              });
            }).catch((error: BusinessError) => {
              console.error(`Failed to create pixel map promise, Code: ${(error as BusinessError).code}, message: ${(error as BusinessError).message}.`);
            });
          });
        }
      )
    }
  }
}
```
