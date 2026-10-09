# @typescript-eslint/lines-between-class-members

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-lines-between-class-members

禁止或者要求类成员之间有空行分隔。
 

## 规则配置

```json
// code-linter.json5
{
  <span style="color: rgb(135,16,148);">"rules"</span>: {
    "@typescript-eslint/lines-between-class-members": "error"
  }
}
```
 
 

## 选项

详情请参考[@typescript-eslint/lines-between-class-members选项](https://typescript-eslint.nodejs.cn/rules/lines-between-class-members/#options)。
 
 

## 正例

```text
// 默认要求类成员之间有空行分隔
export class Foo {
  public baz() {
    console.info('baz');
  }

  public qux() {
    console.info('qux');
  }
}
```
 
 

## 反例

```text
// 默认要求类成员之间有空行分隔
export class Foo {
  public baz() {
    console.info('baz');
  }
  public qux() {
    console.info('qux');
  }
}
```
 
 

## 规则集

```text
<span style="color: rgb(6,125,23);">plugin:@typescript-eslint/all</span>
```
 
Code Linter代码检查规则的配置指导请参考[Code Linter代码检查](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-code-linter)。
