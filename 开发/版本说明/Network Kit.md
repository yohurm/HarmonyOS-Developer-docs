# Network Kit

更新时间：2026-08-29 09:40:02

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-releases/js-apidiff-networkkit-7003

| 操作 | 旧版本 | 新版本 | d.ts文件 |
| --- | --- | --- | --- |
| 新增错误码 | 类名：NetConnection； API声明：unregister(callback: AsyncCallback&lt;void&gt;): void; 差异内容：NA | 类名：NetConnection； API声明：unregister(callback: AsyncCallback&lt;void&gt;): void; 差异内容：201 | api/@ohos.net.connection.d.ts |
| 权限变更 | 类名：statistics； API声明：function getUidRxBytes(uid: number, callback: AsyncCallback&lt;number&gt;): void; 差异内容：ohos.permission.GET_NETWORK_STATS | 类名：statistics； API声明：function getUidRxBytes(uid: number, callback: AsyncCallback&lt;number&gt;): void; 差异内容：ohos.permission.GET_NETWORK_STATS [since 26.0.0] | api/@ohos.net.statistics.d.ts |
| 权限变更 | 类名：statistics； API声明：function getUidRxBytes(uid: number): Promise&lt;number&gt;; 差异内容：ohos.permission.GET_NETWORK_STATS | 类名：statistics； API声明：function getUidRxBytes(uid: number): Promise&lt;number&gt;; 差异内容：ohos.permission.GET_NETWORK_STATS [since 26.0.0] | api/@ohos.net.statistics.d.ts |
| 权限变更 | 类名：statistics； API声明：function getUidTxBytes(uid: number, callback: AsyncCallback&lt;number&gt;): void; 差异内容：ohos.permission.GET_NETWORK_STATS | 类名：statistics； API声明：function getUidTxBytes(uid: number, callback: AsyncCallback&lt;number&gt;): void; 差异内容：ohos.permission.GET_NETWORK_STATS [since 26.0.0] | api/@ohos.net.statistics.d.ts |
| 权限变更 | 类名：statistics； API声明：function getUidTxBytes(uid: number): Promise&lt;number&gt;; 差异内容：ohos.permission.GET_NETWORK_STATS | 类名：statistics； API声明：function getUidTxBytes(uid: number): Promise&lt;number&gt;; 差异内容：ohos.permission.GET_NETWORK_STATS [since 26.0.0] | api/@ohos.net.statistics.d.ts |
| 新增kit | 类名：global； API声明：api@system.fetch.d.ts 差异内容：NA | 类名：global； API声明：api@system.fetch.d.ts 差异内容：NetworkKit | api/@system.fetch.d.ts |
| 新增kit | 类名：global； API声明：api@system.network.d.ts 差异内容：NA | 类名：global； API声明：api@system.network.d.ts 差异内容：NetworkKit | api/@system.network.d.ts |
