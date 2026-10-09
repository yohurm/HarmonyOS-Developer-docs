# @typescript-eslint/ban-types

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-ban-types

不允许使用某些类型。
 

## 规则配置

```json
// code-linter.json5
{
  <span style="color: rgb(135,16,148);">"rules"</span>: {
    "@typescript-eslint/ban-types": "error"
  }
}
```
 
 

## 选项

详情请参考[@typescript-eslint/ban-types选项](https://typescript-eslint.nodejs.cn/rules/ban-types/#options)。
 
 

## 正例

```text
// 类型小写保持一致
const str: string = 'foo';
const bool: boolean = true;
const num: number = 1;
const bigInt: bigint = 1n;

// 使用正确的函数类型
const func: () => string = () => 'hello';

export { str, bool, num, bigInt, func };
```
 
 

## 反例

```text
// 类型小写保持一致
const str: String = 'foo';
const bool: Boolean = true;
const num: Number = 1;
const bigInt: BigInt = 1n;

// 使用正确的函数类型
const func: Function = () => 'hello';

export { str, bool, num, bigInt, func };
```
 
 

## 规则集

```text
<span style="color: rgb(6,125,23);">plugin:@typescript-eslint/all</span>
```
 
Code Linter代码检查规则的配置指导请参考[Code Linter代码检查](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-code-linter)。
