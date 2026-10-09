# @typescript-eslint/explicit-function-return-type

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-explicit-function-return-type

函数和类方法需要显式的定义返回类型。
 
该规则仅支持对.js/.ts文件进行检查。
 

## 规则配置

```json
// code-linter.json5
{
  <span style="color: rgb(135,16,148);">"rules"</span>: {
    "@typescript-eslint/explicit-function-return-type": "error"
  }
}
```
 
 

## 选项

详情请参考[@typescript-eslint/explicit-function-return-type选项](https://typescript-eslint.nodejs.cn/rules/explicit-function-return-type/#options)。
 
 

## 正例

```text
// No return value should be expected (void)
function test(): void {
  return;
}

// A return value of type number
const fn = function (): number {
  return Number.MAX_VALUE;
};

// A return value of type string
const arrowFn = (): string => 'test';

class Test {
  // No return value should be expected (void)
  public method(): void {
    return;
  }
}

export { test, fn, arrowFn, Test };
```
 
 

## 反例

```text
// Should indicate that no value is returned (void)
function test() {
  return;
}

// Should indicate that a number is returned
const fn = function () {
  return Number.MAX_VALUE;
};

// Should indicate that a string is returned
const arrowFn = () => 'test';

class Test {
  // Should indicate that no value is returned (void)
  public method() {
    return;
  }
}

export { test, fn, arrowFn, Test };
```
 
 

## 规则集

```text
<span style="color: rgb(6,125,23);">plugin:@typescript-eslint/recommended</span>
<span style="color: rgb(6,125,23);">plugin:@typescript-eslint/all</span>
```
 
Code Linter代码检查规则的配置指导请参考[Code Linter代码检查](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-code-linter)。
