# ArkWeb

更新时间：2026-08-29 09:40:02

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-releases/js-apidiff-arkweb-7003

| 操作 | 旧版本 | 新版本 | d.ts文件 |
| --- | --- | --- | --- |
| 新增API | NA | 类名：WebviewController； API声明：getSubframeErrorPageEnabled(): boolean; 差异内容：getSubframeErrorPageEnabled(): boolean; | api/@ohos.web.webview.d.ts |
| 新增API | NA | 类名：WebAttribute； API声明：enableMediaNetworkProxy(enabled: boolean): WebAttribute; 差异内容：enableMediaNetworkProxy(enabled: boolean): WebAttribute; | component/web.d.ts |
| 类新增同名方法且参数类型与已有的参数类型范围是包含关系 | 类名：WebCookieManager； API声明：static fetchCookieSync(url: string, incognito?: boolean): string; 差异内容：static fetchCookieSync(url: string, incognito?: boolean): string; | 类名：WebCookieManager； API声明：static fetchCookieSync(url: string, incognito?: boolean, includePartitionedCookies?: boolean): string; 差异内容：static fetchCookieSync(url: string, incognito?: boolean, includePartitionedCookies?: boolean): string; | api/@ohos.web.webview.d.ts |
| 类新增同名方法且参数类型与已有的参数类型范围是包含关系 | 类名：WebviewController； API声明：setErrorPageEnabled(enable: boolean): void; 差异内容：setErrorPageEnabled(enable: boolean): void; | 类名：WebviewController； API声明：setErrorPageEnabled(enable: boolean, includeSubframe: boolean): void; 差异内容：setErrorPageEnabled(enable: boolean, includeSubframe: boolean): void; | api/@ohos.web.webview.d.ts |
| 类新增同名方法且参数类型与已有的参数类型范围不是包含关系 | 类名：WebCookieManager； API声明：static fetchCookie(url: string, callback: AsyncCallback&lt;string&gt;): void; 差异内容：static fetchCookie(url: string, callback: AsyncCallback&lt;string&gt;): void; | 类名：WebCookieManager； API声明：static fetchCookie(url: string, incognito: boolean, includePartitionedCookies: boolean): Promise&lt;string&gt;; 差异内容：static fetchCookie(url: string, incognito: boolean, includePartitionedCookies: boolean): Promise&lt;string&gt;; | api/@ohos.web.webview.d.ts |
