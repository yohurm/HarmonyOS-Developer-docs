# @previewer/mandatory-default-value-for-local-initialization

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-mandatory-default-value-for-local-initialization

如果组件的属性支持本地初始化，需要设置一个合法的不依赖运行时的默认值。
 

## 规则配置

```json
// code-linter.json5
<span style="color: rgb(65,97,0);">{</span>
<span style="color: rgb(65,97,0);">  "rules": {</span>
<span style="color: rgb(65,97,0);">    "@previewer/mandatory-default-value-for-local-initialization": "warn"</span>
<span style="color: rgb(65,97,0);">  }</span>
<span style="color: rgb(65,97,0);">}</span>
```
 
 

## 选项

该规则无需配置额外选项。
 
 

## 正例

```text
<span style="color: rgb(65,97,0);">@</span><span style="color: rgb(65,97,0);">Builder function MyBuilderFunction(): void {}</span>
<span style="color: rgb(65,97,0);">@Entry</span>
<span style="color: rgb(65,97,0);">@Component</span>
<span style="color: rgb(65,97,0);">struct Index {</span>
<span style="color: rgb(65,97,0);">  messageA?: string;</span>
<span style="color: rgb(65,97,0);">  message: string = 'Hello World';</span>
<span style="color: rgb(65,97,0);">  @Provide messageB: string = 'messageB';</span>
<span style="color: rgb(65,97,0);">  @StorageLink('varA') varA: number = 2;</span>
<span style="color: rgb(65,97,0);">  @StorageProp('languageCode') lang: string = 'en';</span>
<span style="color: rgb(65,97,0);">  @LocalStorageLink('PropA') storageLink1: number = 1;</span>
<span style="color: rgb(65,97,0);">  @LocalStorageProp('PropB') storageLink2: number = 2;</span>
<span style="color: rgb(65,97,0);">  @BuilderParam myBuilder: () =</span><span style="color: rgb(65,97,0);">></span><span style="color: rgb(65,97,0);"> void = MyBuilderFunction;</span>
<span style="color: rgb(65,97,0);">  build() {</span>
<span style="color: rgb(65,97,0);">    Row() {</span>
<span style="color: rgb(65,97,0);">      Column() {</span>
<span style="color: rgb(65,97,0);">        Text(this.message)</span>
<span style="color: rgb(65,97,0);">        this.myBuilder()</span>
<span style="color: rgb(65,97,0);">      }</span>
<span style="color: rgb(65,97,0);">    }</span>
<span style="color: rgb(65,97,0);">  }</span>
<span style="color: rgb(65,97,0);">}</span>
```
 
 

## 反例

```text
<span style="color: rgb(155,187,89);">@</span><span style="color: rgb(65,97,0);">Entry</span>
<span style="color: rgb(65,97,0);">@Component</span>
<span style="color: rgb(65,97,0);">struct Index {</span>
<span style="color: rgb(65,97,0);">  @BuilderParam myBuilder: () =</span><span style="color: rgb(65,97,0);">></span><span style="color: rgb(65,97,0);"> void;</span>
<span style="color: rgb(65,97,0);">  build() {</span>
<span style="color: rgb(65,97,0);">    Row() {</span>
<span style="color: rgb(65,97,0);">      Column() {</span>
<span style="color: rgb(65,97,0);">        Text('Hello World')</span>
<span style="color: rgb(65,97,0);">        this.myBuilder()</span>
<span style="color: rgb(65,97,0);">      }</span>
<span style="color: rgb(65,97,0);">    }</span>
<span style="color: rgb(65,97,0);">  }</span>
<span style="color: rgb(65,97,0);">}</span>
```
 
 

## 规则集

```text
<span style="color: rgb(106,135,89);">plugin:@previewer/recommended</span>
<span style="color: rgb(106,135,89);">plugin:@previewer/all</span>
```
 
Code Linter代码检查规则的配置指导请参考[Code Linter代码检查](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-code-linter)。
