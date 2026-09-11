# MDM Kit

更新时间：2026-08-29 09:40:02

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-releases/js-apidiff-mdmkit-7003

| 操作 | 旧版本 | 新版本 | d.ts文件 |
| --- | --- | --- | --- |
| 新增错误码 | 类名：deviceControl； API声明：function operateDevice(admin: Want, operation: Operation, addition?: string): void; 差异内容：NA | 类名：deviceControl； API声明：function operateDevice(admin: Want, operation: Operation, addition?: string): void; 差异内容：9201048 | api/@ohos.enterprise.deviceControl.d.ts |
| 删除错误码 | 类名：systemManager； API声明：function isOtaUpdateNonceEnable(admin: Want): boolean; 差异内容：801 | 类名：systemManager； API声明：function isOtaUpdateNonceEnable(admin: Want): boolean; 差异内容：NA | api/@ohos.enterprise.systemManager.d.ts |
| 权限变更 | 类名：usbManager； API声明：function getUsbStorageDeviceAccessPolicy(admin: Want \| null): UsbPolicy; 差异内容：ohos.permission.ENTERPRISE_MANAGE_USB or ohos.permission.PERSONAL_MANAGE_RESTRICTIONS [since 26.0.0] | 类名：usbManager； API声明：function getUsbStorageDeviceAccessPolicy(admin: Want \| null): UsbPolicy; 差异内容：ohos.permission.ENTERPRISE_MANAGE_USB or ohos.permission.PERSONAL_MANAGE_RESTRICTIONS | api/@ohos.enterprise.usbManager.d.ts |
| 函数变更 | 类名：restrictions； API声明：function getUserRestricted(admin: Want, settingsItem: SettingsForDevice): boolean; 差异内容：admin: Want | 类名：restrictions； API声明：function getUserRestricted(admin: Want \| null, settingsItem: SettingsForDevice): boolean; 差异内容：admin: Want \| null | api/@ohos.enterprise.restrictions.d.ts |
