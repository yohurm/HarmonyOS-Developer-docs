# @security/no-unsafe-hash

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-no-unsafe-hash

该规则禁止使用不安全的哈希算法，例如MD5、SHA1。
 

## 规则配置

```json
// code-linter.json5
{
  <span style="color: rgb(135,16,148);">"rules"</span>: {
    <span style="color: rgb(135,16,148);">"@security/no-unsafe-hash"</span>: <span style="color: rgb(6,125,23);">"error"</span>
  }
}
```
 
 

## 选项

该规则无需配置额外选项。
 
 

## 正例

```text
import cryptoFramework from '@ohos.security.cryptoFramework';
cryptoFramework.createMd('SHA256');

import { CryptoJS } from '@ohos/crypto-js';
CryptoJS.SHA256('Message').toString();
```
 
 

## 反例

```text
import cryptoFramework from '@ohos.security.cryptoFramework';
cryptoFramework.createMd('MD5');

import { CryptoJS } from '@ohos/crypto-js';
CryptoJS.MD5('Message').toString();
```
 
 

## 规则集

```text
<span style="color: rgb(6,125,23);">plugin:@security/recommended</span>
<span style="color: rgb(6,125,23);">plugin:@security/all</span>
```
 
Code Linter代码检查规则的配置指导请参考[Code Linter代码检查](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-code-linter)。
