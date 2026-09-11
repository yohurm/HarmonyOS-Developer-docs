# @security/no-unsafe-ecdh

更新时间：2026-08-29 09:41:34

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide_no-unsafe-ecdh

此规则禁止使用不安全的非对称密钥类型ECC。推荐使用ECC256算法，详情参见：[密钥生成算法](https://developer.huawei.com/consumer/cn/doc/AppGallery-connect-Guides/aegis-key-generation-0000001819355432)。
 

## 规则配置

```json
// code-linter.json5
{
  "rules": {
    "@security/no-unsafe-ecdh": "warn"
  }
}
```
 
 

## 选项

该规则无需配置选项。
 
 

## 正例

```text
import cryptoFramework from '@ohos.security.cryptoFramework';
cryptoFramework.createAsyKeyGenerator('ECC256');
```
 
 

## 反例

```text
import cryptoFramework from '@ohos.security.cryptoFramework';
cryptoFramework.createAsyKeyGenerator('ECC');
```
 
 

## 规则集

```text
plugin:@security/all
```
 
Code Linter代码检查规则的配置指导请参考[Code Linter代码检查](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-code-linter)。
