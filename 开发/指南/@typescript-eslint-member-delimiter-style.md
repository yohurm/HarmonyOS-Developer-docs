# @typescript-eslint/member-delimiter-style

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-member-delimiter-style

要求接口和类型别名中的成员之间使用特定的分隔符。
 
支持定义的分隔符有三种：分号、逗号、无分隔符。
 

## 规则配置

```json
// code-linter.json5
{
  <span style="color: rgb(135,16,148);">"rules"</span>: {
    "@typescript-eslint/member-delimiter-style": "error"
  }
}
```
 
 

## 选项

详情请参考[@typescript-eslint/member-delimiter-style选项](https://typescript-eslint.nodejs.cn/rules/member-delimiter-style/#options)。
 
 

## 正例

```text
// 默认接口/类型别名定义为多行的场景下，每个成员应以分号 (;) 分隔。 最后一个成员必须有一个分隔符。
// 默认接口/类型别名定义为单行的场景下，每个成员应以分号 (;) 分隔。最后一个成员不能有分隔符。
// 接口/类型别名中的任何换行符都会使其成为多行。
export interface Foo1 {
  name: string;

  greet(): string;
}

export interface Foo2 { name: string }
```
 
 

## 反例

```text
// missing semicolon delimiter
export interface Foo {
  name: string
  greet(): string
}

// using incorrect delimiter
export interface Bar {
  name: string,
  greet(): string,
}

// missing last member delimiter
export interface Baz {
  name: string;
  greet(): string
}
```
 
 

## 规则集

```text
<span style="color: rgb(6,125,23);">plugin:@typescript-eslint/all</span>
```
 
Code Linter代码检查规则的配置指导请参考[Code Linter代码检查](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-code-linter)。
