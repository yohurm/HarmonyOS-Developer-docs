# @typescript-eslint/type-annotation-spacing

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-type-annotation-spacing

类型注释前后需要一致的空格风格。
 

## 规则配置

```json
// code-linter.json5
{
  <span style="color: rgb(135,16,148);">"rules"</span>: {
    "@typescript-eslint/type-annotation-spacing": "error"
  }
}
```
 
 

## 选项

详情请参考[@typescript-eslint/type-annotation-spacing选项](https://typescript-eslint.nodejs.cn/rules/type-annotation-spacing/#options)。
 
 

## 正例

```text
// 默认冒号前无空格，冒号后有空格
export const foo1: string = 'bar';

export declare function foo2(): string;

export class Foo3 {
  public name: string = 'hello';
}
// 默认箭头前后都有空格
export declare type Foo4 = () => void;
```
 
 

## 反例

```text
// 默认冒号前无空格，冒号后有空格
export const foo1 :string = 'bar';

export declare function foo2() :string;

export class Foo3 {
  public name :string = 'hello';
}
// 默认箭头前后都有空格
export declare type Foo4 = ()=>void;
```
 
 

## 规则集

```text
<span style="color: rgb(6,125,23);">plugin:@typescript-eslint/all</span>
```
 
Code Linter代码检查规则的配置指导请参考[Code Linter代码检查](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-code-linter)。
