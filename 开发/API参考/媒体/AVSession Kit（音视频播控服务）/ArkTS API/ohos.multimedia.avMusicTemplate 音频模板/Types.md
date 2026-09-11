# Types

更新时间：2026-08-29 09:41:17

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/arkts-apis-avmusictemplate-t
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

> [!NOTE]
> 本模块首批接口从API version 23开始支持。后续版本的新增接口，采用上角标单独标记接口的起始版本。 本模块仅适用于API version 23及以上版本的Car设备。



## NoParamAsyncCallback


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type NoParamAsyncCallback = () => Promise&lt;void&gt;

定义无参数的异步回调函数类型。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;void&gt; | Promise对象，无返回结果。 |




## QueryMainTabsEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type QueryMainTabsEvent = () => Promise<MediaTab[]>

主标签页查询事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise<MediaTab[]> | Promise对象，返回媒体标签页的集合。 |




## QueryMediaTabContentEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type QueryMediaTabContentEvent = (tabId: string) => Promise&lt;MediaTabContent&gt;

媒体标签页内容查询事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| tabId | string | 是 | 标签页的ID。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;MediaTabContent&gt; | Promise对象，返回媒体标签页内容。 |




## QueryMediaEntityEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type QueryMediaEntityEvent = (params: QueryMediaEntityParam) => Promise&lt;PageMediaEntity&gt;

媒体实体查询事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| params | QueryMediaEntityParam | 是 | 查询媒体实体的参数。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;PageMediaEntity&gt; | Promise对象，返回查询的媒体实体分页对象。 |




## QueryCompilationEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type QueryCompilationEvent = (compilationId: string, pageIndex: number) => Promise&lt;PageMediaEntity&gt;

合集查询事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| compilationId | string | 是 | 合集的ID。 |
| pageIndex | number | 是 | 页面的索引。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;PageMediaEntity&gt; | Promise对象，返回查询的合集媒体实体对象。 |




## QueryPlaylistEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type QueryPlaylistEvent = (pageIndex: number, sort: Sort) => Promise&lt;PageMediaEntity&gt;

播放列表查询事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| pageIndex | number | 是 | 页面的索引。 |
| sort | Sort | 是 | 排序类型。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;PageMediaEntity&gt; | Promise对象，返回查询的播放列表的分页对象。 |




## QueryCurrentSingleEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type QueryCurrentSingleEvent = () => Promise&lt;Single&gt;

当前单曲查询事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;Single&gt; | Promise对象，返回Single对象。 |




## QueryCompilationByKeywordEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type QueryCompilationByKeywordEvent = (keyword: string) => Promise<Compilation[]>

按关键字查询合集的事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| keyword | string | 是 | 用于查找合集的关键字。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise<Compilation[]> | Promise对象，返回与关键字相关的合集数组。 |




## QueryMediaEntityByKeywordEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type QueryMediaEntityByKeywordEvent = (keyword: string, searchType: EntityType, pageIndex: number) => Promise&lt;PageMediaEntity&gt;

按关键字查询媒体实体的事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| keyword | string | 是 | 用于查找媒体的关键字。 |
| searchType | EntityType | 是 | 要搜索的媒体资源类型。 |
| pageIndex | number | 是 | 页面的索引。从0开始。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;PageMediaEntity&gt; | Promise对象，返回关键字相关的媒体实体的分页对象。 |




## QueryRecommendMediaEntityListEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type QueryRecommendMediaEntityListEvent = () => Promise<MediaEntity[]>

推荐媒体实体列表查询事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise<MediaEntity[]> | Promise对象，返回推荐的媒体实体的数组。 |




## QueryHotWordsEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type QueryHotWordsEvent = () => Promise<string[]>

热词查询事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise<string[]> | Promise对象，返回热词的数组。 |




## QuerySearchHistoryEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type QuerySearchHistoryEvent = () => Promise<string[]>

搜索历史查询事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise<string[]> | Promise对象，返回搜索历史的数组。 |




## ClearSearchHistoryEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type ClearSearchHistoryEvent = () => Promise&lt;OperResult&gt;

清除搜索历史事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;OperResult&gt; | Promise对象，返回清除搜索历史的操作结果的对象。 |




## LoginEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type LoginEvent = (controlType: LoginType, id?: string) => Promise<QrCodeInfo[]>

登录事件。用于控制登录流程，包括查询登录信息、刷新登录信息、取消操作和退出登录。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| controlType | LoginType | 是 | 登录类型。 |
| id | string | 否 | 二维码ID。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise<QrCodeInfo[]> | Promise对象，返回二维码信息的数组。 |




## LoginType


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type LoginType = 'queryLoginInfo' | 'refreshLoginInfo' | 'cancel' | 'logout'

登录的类型。该类型可取的值为下表字符串。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate


| 类型 | 说明 |
| --- | --- |
| 'queryLoginInfo' | 查询登录信息。 |
| 'refreshLoginInfo' | 刷新登录信息。 |
| 'cancel' | 取消。 |
| 'logout' | 退出登录。 |




## RequestDialogInfoEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type RequestDialogInfoEvent = (actionType: DialogActionType, actionInfo?: DialogActionInfo) => Promise&lt;DialogInfo&gt;

对话框信息请求事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| actionType | DialogActionType | 是 | 对话框操作类型。 |
| actionInfo | DialogActionInfo | 否 | 对话框动作结果的信息。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;DialogInfo&gt; | Promise对象，返回对话框信息。 |




## DialogActionType


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type DialogActionType = 'open' | 'close' | 'refresh'

对话框操作类型。该类型可取的值为下表字符串。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate


| 类型 | 说明 |
| --- | --- |
| 'open' | 打开。 |
| 'close' | 关闭。 |
| 'refresh' | 刷新。 |




## HandleMemberPurchaseEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type HandleMemberPurchaseEvent = (info: MemberPurchaseInfo) => Promise&lt;DialogInfo&gt;

处理购买会员事件。系统会在用户触发购买操作时调用此事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| info | MemberPurchaseInfo | 是 | 购买会员的信息。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;DialogInfo&gt; | Promise对象，返回对话框信息。 |




## QueryMemberPurchaseEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type QueryMemberPurchaseEvent = (memberPurchaseType: MemberPurchaseType) => Promise<MemberPurchaseInfo[]>

购买会员查询事件。用于根据会员购买类型查询可用的会员购买信息，系统会在用户进入会员购买页面时调用此事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| memberPurchaseType | MemberPurchaseType | 是 | 购买会员的类型。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise<MemberPurchaseInfo[]> | Promise对象，返回会员购买信息的数组。 |




## QueryCustomContentEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type QueryCustomContentEvent = (queryType: CustomType[]) => Promise&lt;CustomElement&gt;

自定义内容查询事件。用于查询用户基本信息、界面选项卡配置、代码编译选项和系统设置项等自定义内容。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| queryType | CustomType[] | 是 | 自定义类型：包含用户基本信息、界面选项卡配置、代码编译选项和系统设置项。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;CustomElement&gt; | Promise对象，返回我的页面的自定义元素。 |




## CustomType


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type CustomType = 'USER_INFO' | 'TAB' | 'COMPILATION' | 'SETTINGS'

自定义类型。该类型可取的值为下表字符串。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate


| 类型 | 说明 |
| --- | --- |
| 'USER_INFO' | 用户信息。 |
| 'TAB' | 选项卡。 |
| 'COMPILATION' | 合集。 |
| 'SETTINGS' | 设置。 |




## DownloadMediaEntityEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type DownloadMediaEntityEvent = (controlType: DownloadControlType, mediaEntity: MediaEntity) => Promise&lt;OperResult&gt;

媒体实体下载事件。用于控制媒体实体的下载流程，支持开始下载、暂停下载、恢复下载和删除下载操作。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| controlType | DownloadControlType | 是 | controlType的可选项包括：开始下载、删除下载、恢复下载、暂停下载。 |
| mediaEntity | MediaEntity | 是 | 媒体实体。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;OperResult&gt; | Promise对象，返回下载媒体实体的操作结果对象。 |




## DownloadControlType


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type DownloadControlType = 'startDownload' | 'deleteDownload' | 'resumeDownload' | 'pauseDownload'

下载操作控制类型。该类型可取的值为下表字符串。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate


| 类型 | 说明 |
| --- | --- |
| 'startDownload' | 开始下载。 |
| 'deleteDownload' | 删除下载。 |
| 'resumeDownload' | 恢复下载。 |
| 'pauseDownload' | 暂停下载。 |




## SettingsChangeEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type SettingsChangeEvent = (settingItem: SettingItem) => Promise&lt;SettingItem&gt;

设置变更事件类型。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| settingItem | SettingItem | 是 | 设置项。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;SettingItem&gt; | Promise对象，返回变更过的设置项。 |




## ProblemAndAdviceEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type ProblemAndAdviceEvent = (advice: string) => Promise&lt;OperResult&gt;

问题和建议事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| advice | string | 是 | 问题和建议的内容。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;OperResult&gt; | Promise对象，返回问题和建议的操作结果对象。 |




## PlayForSearchEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type PlayForSearchEvent = (command: SearchPlayInfoType, args: SearchPlayInfo) => Promise&lt;OperResult&gt;

搜索并播放媒体的事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| command | SearchPlayInfoType | 是 | 搜播信息的类型。 |
| args | SearchPlayInfo | 是 | 搜播信息。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;OperResult&gt; | Promise对象，返回搜播的操作结果对象。 |




## ExecuteActionEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type ExecuteActionEvent = (actionType: string, params: string) => Promise&lt;string&gt;

执行操作事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| actionType | string | 是 | 动作类型。 |
| params | string | 是 | 参数信息。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;string&gt; | Promise对象，返回执行操作的结果字符串。 |




## PlayMediaEntityEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type PlayMediaEntityEvent = (mediaEntity: MediaEntity) => Promise&lt;void&gt;

媒体实体播放事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| mediaEntity | MediaEntity | 是 | 需要播放的媒体实体。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;void&gt; | Promise对象，无返回结果。 |




## FavoriteMediaEntityEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type FavoriteMediaEntityEvent = (actionType: MediaFavoriteType, mediaEntity: MediaEntity) => Promise&lt;OperResult&gt;

媒体实体收藏事件。使用Promise异步回调。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| actionType | MediaFavoriteType | 是 | 操作类型。 |
| mediaEntity | MediaEntity | 是 | 媒体实体。 |


**返回值：**


| 类型 | 说明 |
| --- | --- |
| Promise&lt;OperResult&gt; | Promise对象，返回收藏媒体实体的操作结果对象。 |




## MediaFavoriteType


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type MediaFavoriteType = 'addFavorite' | 'removeFavorite'

媒体收藏类型的定义。该类型可取的值为下表字符串。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate


| 类型 | 说明 |
| --- | --- |
| 'addFavorite' | 添加收藏。 |
| 'removeFavorite' | 取消收藏。 |




## DialogControlType


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type DialogControlType = 'open' | 'close' | 'refresh' | 'toast'

对话框控制类型的定义。该类型可取的值为下表字符串。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate


| 类型 | 说明 |
| --- | --- |
| 'open' | 打开。 |
| 'close' | 关闭。 |
| 'refresh' | 刷新。 |
| 'toast' | 提示。 |




## ActionType


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type ActionType = 'add' | 'remove'

操作类型的定义。该类型可取的值为下表字符串。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate


| 类型 | 说明 |
| --- | --- |
| 'add' | 添加。 |
| 'remove' | 移除。 |




## ReportDialogCommandEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type ReportDialogCommandEvent = (type: DialogControlType, buttonInfo: DialogInfo) => void

对话框命令上报事件。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| type | DialogControlType | 是 | 对话框控制类型。 |
| buttonInfo | DialogInfo | 是 | 对话框信息。 |




## ReportTabContentEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type ReportTabContentEvent = (tabId: string, tabContent: MediaTabContent) => void

标签页内容上报事件。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| tabId | string | 是 | 标签页的ID。 |
| tabContent | MediaTabContent | 是 | 标签页的内容。 |




## ReportCustomElementsChangeEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type ReportCustomElementsChangeEvent = (actionType: ActionType, customType: CustomType, customElement: CustomElement) => void

上报自定义元素改变事件。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| actionType | ActionType | 是 | 操作类型。 |
| customType | CustomType | 是 | 自定义类型。 |
| customElement | CustomElement | 是 | 自定义元素。 |




## ReportExecuteActionEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type ReportExecuteActionEvent = (actionType: string, params: string) => void

执行动作上报事件。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| actionType | string | 是 | 操作类型。 |
| params | string | 是 | 执行动作的信息。 |




## ReportExecuteAbilityEvent


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

type ReportExecuteAbilityEvent = (want: WantAgent) => void

通知音频模板控制方拉起指定媒体应用界面事件。

**模型约束：** 此接口仅可在Stage模型下使用。

**系统能力：** SystemCapability.Multimedia.AVSession.AVMusicTemplate

**参数：**


| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| want | WantAgent | 是 | 媒体应用页面启动信息。 |
