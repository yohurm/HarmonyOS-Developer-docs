# @correctness/redundant-dependency-check

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-redundant-dependency-check

建议删除冗余的依赖配置。冗余依赖会增加加载和解析时间，影响代码质量。
 

## 规则配置

```json
// code-linter.json5
{
  "rules": {
    "@correctness/redundant-dependency-check": "suggestion"
  }
}
```
 
 

## 选项

该规则无需配置选项。
 
 

## 正例

1. 在entry下的oh-package.json5文件中配置了a、b、c三个依赖，entry/src/main/ets中的文件中全部导入。
 
2. 在工程级的oh-package.json5文件中配置了a、b、c三个依赖，整个工程全部导入。
 
 

## 反例

1. 在entry下的oh-package.json5文件中配置了a、b、c三个依赖，但entry/src/main/ets中的文件中只导入了a和b两个依赖。
 
2. 在工程级的oh-package.json5文件中配置了a、b、c三个依赖，但整个工程只导入了a,b两个依赖。
 
 

## 规则集

```text
<span style="color: rgb(80,160,79);">plugin:@correctness/all</span>
```
 
Code Linter代码检查规则的配置指导请参考[Code Linter代码检查](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-code-linter)。
