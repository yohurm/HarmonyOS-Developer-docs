# 使用云存储上传文件失败，app日志提示“"state":65”，upload进程日志提示“403 Forbidden”

更新时间：2026-09-09 06:54:05

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/cloudfoundation-faq-2

**问题现象**

使用云存储上传文件失败，出现如下错误提示：

 - app日志提示“"state":65”

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a6/v3/4ZXIIlavQYCS6-dliD7PeQ/zh-cn_image_0000002747211619.png?HW-CC-KV=V1&HW-CC-Date=20260911T072716Z&HW-CC-Expire=86400&HW-CC-Sign=378C86ADC2A529D1F21AC1D1F1C173654F849336C682A0E2F5CE879FC398A51F)

 - upload进程的日志提示“403 Forbidden”（通过设置“No filters”模式、过滤“C01C50”关键字查找）

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/b9/v3/awwhRdyXSGK3mDLGaBGn6A/zh-cn_image_0000002717771684.png?HW-CC-KV=V1&HW-CC-Date=20260911T072716Z&HW-CC-Expire=86400&HW-CC-Sign=8100FC0622A6A6DA2DD14106639E44383DB09C4E8721E7C002D03A3FFC32C957)



**解决措施**

出现此问题，可按照如下步骤排查和解决：
1. 请确认应用的签名方式正确。当前Cloud Foundation Kit支持[关联注册应用进行自动签名](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-signing-auto#section6333421192714)和[手动签名](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-signing-manual)两种方式。
2. 请确认已通过[AuthProvider](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/cloudfoundation-cloudcommon#authprovider)获取用户凭据。未配置用户凭据的情况下，服务端会返回“403 Forbidden”错误。
