# oh_pointer_style.h

更新时间：2026-09-17 01:44:14

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-oh-pointer-style-h
**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

## 概述


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

鼠标光标的样式。
 
**引用文件：** <multimodalinput/oh_pointer_style.h>
 
**库：** libohinput.so
 
**系统能力：** SystemCapability.MultimodalInput.Input.Core
 
**起始版本：** 22
 
**相关模块：** [input](https://developer.huawei.com/consumer/cn/doc/harmonyos-references/capi-input)
 
  

## 汇总


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### 枚举


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable
 

| 名称 | typedef关键字 | 描述 |
| --- | --- | --- |
| Input_PointerStyle | Input_PointerStyle | 鼠标光标样式。 |
 
 
  

## 枚举类型说明


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

  

### Input_PointerStyle


**支持设备：** Phone | PC/2in1 | Tablet | TV | Wearable

```text
enum Input_PointerStyle
```
 
**描述**
 
鼠标光标样式。
 
**起始版本：** 22
  

| 枚举项 | 描述 | 图示 |
| --- | --- | --- |
| DEFAULT = 0 | 应用未设置时显示的光标样式。 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/14/v3/02GWRK3UQMi_YAiRKfkEHw/zh-cn_image_0000002749495556.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=993B1375CB077C1EE0404F7E7812FD37B8F1667798BC2C28A717EEDEB54E0AA0) |
| EAST = 1 | 向东箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/5b/v3/zQJ-tHvZS7WurwPH0-CdEQ/zh-cn_image_0000002779094613.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=4F1E12307DDFDC897949818A386452662D79D26B8179A74D9A6B27FE4C4516AB) |
| WEST = 2 | 向西箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/2a/v3/TRqIY_ddT3Kna140Kx1Z7A/zh-cn_image_0000002778934759.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=70A012A2A8DA6375CF8ABF4770105C03E2DD371B4A10FBC76CBEF30447245CBB) |
| SOUTH = 3 | 向南箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/94/v3/Dck0D5FITjmPHUzwV5-uew/zh-cn_image_0000002749335674.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=901E62AE9DC21592F28357B1C222030F841CCAEFEA8DC336AD0569B4B98CDB9F) |
| NORTH = 4 | 向北箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/90/v3/S66SHohDTpekMuFVCDo1wg/zh-cn_image_0000002749495558.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=FF4A91871D7B561081C20B6F60F6C247ADF67B46CAC91435EE023864F683A20A) |
| WEST_EAST = 5 | 向西东箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/52/v3/rBqM5HqDQDKxMLi6iow4vg/zh-cn_image_0000002779094615.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=0A7887C088E0D3956B65346855B3174E8059D0C51ACD10160BCEB9B913D79AC8) |
| NORTH_SOUTH = 6 | 向北南箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ef/v3/g56i9mQzRDShWNqTzS4VLA/zh-cn_image_0000002778934761.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=54BA3BDF05A2B654AF19DC8D67BA89E84CEACB119CE6FA66818C09A8A02A6793) |
| NORTH_EAST = 7 | 向东北箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/d/v3/CP0tY5ImTniXi6GT--vZRg/zh-cn_image_0000002749335676.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=BAE59ED95373D62E13B60F39E782A0F6781904AB1D273F9F8C0348C89089168E) |
| NORTH_WEST = 8 | 向西北箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/5d/v3/7osaKMr8Rs-lTYK_Rv4vgw/zh-cn_image_0000002749495560.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=606B97F6BF5ECFDD6E88E747DDADFBA5015FDFCB46D50E4EF9E51420D43831C2) |
| SOUTH_EAST = 9 | 向东南箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/36/v3/IQfTJDH6SLSYrDExHw3I8g/zh-cn_image_0000002779094617.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=4A5DFB37751AA99A94846A81AFCCA7A6A7A7341EDD76D36CEC26B1A2527AA883) |
| SOUTH_WEST = 10 | 向西南箭头 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4c/v3/jEfJUMMUQQ2TGKL-Gwat4w/zh-cn_image_0000002778934763.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=4E9D130D8A7CE8738298AADC16801D8F34C5B5314542A3C34A3D3AF3048762B9) |
| NORTH_EAST_SOUTH_WEST = 11 | 东北西南调整 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/8d/v3/AlOqA4k1RaGOs_qh-TTNuA/zh-cn_image_0000002749335678.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=8F1F18325212FAFC7728BA7FD51DED08E353F5CA4D936477E0DA80A44461B35A) |
| NORTH_WEST_SOUTH_EAST = 12 | 西北东南调整 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4f/v3/z0jLgOIZR6mPFrEhxGcNSA/zh-cn_image_0000002749495562.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=8C8E1AA331ABB29CB51069100FF7C7C1A26EFD101B314E195BF193221AD2E4E8) |
| CROSS = 13 | 准确选择 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/81/v3/LymQtLCuTxWHeGN0Ww4zJQ/zh-cn_image_0000002779094619.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=0BAF361738512E014D13EEA6604F85227D1C2F70DC99BEBBF6B6B47A94C34EDC) |
| CURSOR_COPY = 14 | 复制 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/38/v3/tj9HRas2S3SMtG3armvLhA/zh-cn_image_0000002778934765.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=3B80E010215260E0DE0C30010CDC76CCE2DE1711353C41A0DC19811FFB2F4A27) |
| CURSOR_FORBID = 15 | 不可用 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/6e/v3/naeefG8OSde_Tv0vhvXJAQ/zh-cn_image_0000002749335680.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=18035FD2BC952F2A2E889AABBAFA07B20AF3A4D13E3EC86060C0011C0507DF24) |
| COLOR_SUCKER = 16 | 取色器 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/26/v3/uoq8tZd0Sam7UvFZHj2vAA/zh-cn_image_0000002749495564.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=BCE02AC51629DE73DCEDD8FD33AE83FD6241D0B2797304B9033CFECBC877ACFE) |
| HAND_GRABBING = 17 | 并拢的手 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/3a/v3/fbEaq6oOSHGdBBaksCyLYw/zh-cn_image_0000002779094621.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=986A9D564357AB792BCAF57E0C4CD69E2FD59949704254DA083023B50DAB339E) |
| HAND_OPEN = 18 | 张开的手 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/de/v3/9-qzdb2ATVCwC9tv4NV6EQ/zh-cn_image_0000002778934767.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=EC3B137998F105489EFA4B54C183540DF8B1E1A7C2833896A8BE1C29C9CE1A95) |
| HAND_POINTING = 19 | 手形指针 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/f/v3/RgJ4xqVeT6qw7xGzSEQm3Q/zh-cn_image_0000002749335682.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=5A01E14B77B50C3E37E350300CDF125DE7045EF3F302502B0D9B104C159281F9) |
| HELP = 20 | 帮助选择 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/98/v3/uXhEABjcTeO67ElKV8yo6w/zh-cn_image_0000002749495566.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=FC19D81912F01C1E8A0F682B9306338227F5F26DF921DA1916C258EED1C4D0B7) |
| MOVE = 21 | 移动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/5b/v3/_QuXIakdSsyKBvmwH5m0lA/zh-cn_image_0000002779094623.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=7ADBFA06165F9926E1A16E4B9B3B23CEF142F62B53696758BD2446E647B90BE5) |
| RESIZE_LEFT_RIGHT = 22 | 内部左右调整 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/e1/v3/45GaSuyQS7mZzX5Xe9Txuw/zh-cn_image_0000002778934769.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=9D9CF7F5E22576BB7A942AE4A157791A4E4E9531FE929DCF81F6B6571CB03A63) |
| RESIZE_UP_DOWN = 23 | 内部上下调整 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/31/v3/k6iLNOj0SLavTG6e3uA-CA/zh-cn_image_0000002749335684.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=22360CC56655D0C0197FCF951272185484563A0771CF2E8C5D544810E2015D50) |
| SCREENSHOT_CHOOSE = 24 | 截图十字准星 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/fb/v3/ksxtwv6ZRRSO581Ln4AhDQ/zh-cn_image_0000002749495568.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=BA6B1C6CC4DAB428640C128800682112C4718A6848D8ADADCA31B6FA6B8BC272) |
| SCREENSHOT_CURSOR = 25 | 截图 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/1a/v3/GvreMs7HSrCAbcnh_kB8jQ/zh-cn_image_0000002779094625.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=A2BAACC0F40EBC4F1DD68D03182E499E9C7F33FC8CCF31A7115D0A577BD87B93) |
| TEXT_CURSOR = 26 | 文本选择 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/6b/v3/Q2WEbOXVRumV2zjIrlnUjg/zh-cn_image_0000002778934771.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=240CDB33887EAE462F3A661651AD067750C7EC8B95FE68AF6CA582985176D272) |
| ZOOM_IN = 27 | 放大 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4e/v3/3a-teAeAQOi8cdLDshRHqA/zh-cn_image_0000002749335686.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=F982A4A8DF67BD249732393341908A8A228F2C8CF23CDF6AEB383828274926CB) |
| ZOOM_OUT = 28 | 缩小 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/cd/v3/4JySbAkQRROYRCjevlogcw/zh-cn_image_0000002749495570.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=E6C2D0928FD7874EA4FAC82DF16D0635F44490916C9408AA1F1FBC398A483B93) |
| MIDDLE_BTN_EAST = 29 | 向东滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/42/v3/jNElxYETQxGRteN6kjleMQ/zh-cn_image_0000002779094627.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=0EFBEC7F792641BA845B3D50C552C2D47DA927893EF242207BEB93B249D7FDA5) |
| MIDDLE_BTN_WEST = 30 | 向西滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/fd/v3/fFNa14UiRhuYhyWpbNwzWw/zh-cn_image_0000002778934773.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=9E25F449CFA0DD83A1C992E522840A07257F2C208887DA2E970C32F1AD6FC058) |
| MIDDLE_BTN_SOUTH = 31 | 向南滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/33/v3/9JUJa7y_Sx2ICWSU7Mc-rQ/zh-cn_image_0000002749335688.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=638903C0289CD1606D097E729E53709E3F9B74763B528E42F1DE7C8310CDE395) |
| MIDDLE_BTN_NORTH = 32 | 向北滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/2d/v3/n-Gx6nkSRtKaEGKDhfmkCQ/zh-cn_image_0000002749495572.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=8AA50650035EB971C7D01C919253C35C978A16F71FDE3E32275D22B3A40C2583) |
| MIDDLE_BTN_NORTH_SOUTH = 33 | 向南北滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a4/v3/DuSZnyeaRfSqjKLbMiSFDQ/zh-cn_image_0000002779094629.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=5309B031FFE7F98CD8A100D7E54712F960CDC10794245ADAE55A622085DE064E) |
| MIDDLE_BTN_NORTH_EAST = 34 | 向东北滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ac/v3/7VW4htPwRUCg9looLMWu-Q/zh-cn_image_0000002778934775.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=68EE1831CBBC3ACEAFA4CAF57068E0406DDA427EEDE6D60AD4394C727923731C) |
| MIDDLE_BTN_NORTH_WEST = 35 | 向西北滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4/v3/Ss84IFClQBWpV9DZMyYr-g/zh-cn_image_0000002749335690.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=03E40B039F4DA5DF0A2FCF8487145858C1BDD397FADE4BD662805DE6FA87F03D) |
| MIDDLE_BTN_SOUTH_EAST = 36 | 向东南滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/fd/v3/b2BeuzxvSIGL2GIq23GcOA/zh-cn_image_0000002749495574.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=111069201A4A83874191049EAB558C81AB4667A03E37EB7EA90A52B156498877) |
| MIDDLE_BTN_SOUTH_WEST = 37 | 向西南滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/87/v3/4il5W_vOQ5WXsBMKdDXQDA/zh-cn_image_0000002779094631.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=2CDF6A4652E504F85667CD5361E927DF2AEE45A85F8448322A4DA2F8B2AF4E0D) |
| MIDDLE_BTN_NORTH_SOUTH_WEST_EAST = 38 | 四向锥形移动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a4/v3/0G83VcUTTp-8WXPPTuytoQ/zh-cn_image_0000002778934777.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=5EDE959027D555732A285C81F27C9C6CF97866D96B3CE89F49477609163D187F) |
| HORIZONTAL_TEXT_CURSOR = 39 | 水平文本选择 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/8b/v3/zyv0gGEsTyambTZTzKyuGA/zh-cn_image_0000002749335692.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=13342E6057E6F498B3C35E0D4C9637630FEA84EDE3F056C1F86BDAD2E3FA8D86) |
| CURSOR_CROSS = 40 | 十字光标 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/41/v3/JECZGl97TXupXPN0z-sKYA/zh-cn_image_0000002749495576.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=3ED9B501D2DAF5DC63E8076128E992036229ED23018F0B7037CA7E4A6EDB9C9A) |
| CURSOR_CIRCLE = 41 | 圆形光标 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/89/v3/FCC9TO0MQuSx4eYyeK17Og/zh-cn_image_0000002779094633.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=B376005ADACFDA2894742F3673D7D5C151A7D0CA3271598DDF43DF01D1906CE2) |
| LOADING = 42 | 正在载入动画光标 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ad/v3/gs2boDNnRn-cniIZBBEyMw/zh-cn_image_0000002778934779.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=4A46AB375C89B1E3A1AD4A0733BD9587C9F8782BEE37DDAA5120ABAE481B8B5F) |
| RUNNING = 43 | 后台运行中动画光标 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/b3/v3/T-q9k0raTKaBSY0uqPlg6w/zh-cn_image_0000002749335694.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=F78F6C772A9CC33A2D5C67E5DD300DC3F52577884DC182C874FD1E4E9408E346) |
| MIDDLE_BTN_EAST_WEST = 44 | 向东西滚动 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/97/v3/8gXaUvs_SXKRSC1yb1bSIw/zh-cn_image_0000002749495578.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=D161E0ABAFCF492D453AB8A5834337E109C8DF5111746F8F8F7285E908FB8D25) |
| RUNNING_LEFT = 45 | 后台运行中动画光标（拓展1） | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ee/v3/Rwoxo4QKR8-GBUMiMzLaaQ/zh-cn_image_0000002779094635.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=615907F706E40C98EDECA0978A3EED03C93679C5858AA59F466012281C960BAD) |
| RUNNING_RIGHT = 46 | 后台运行中动画光标（拓展2） | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/6f/v3/aen-Xv1eQ2u8eyW6PGLAPg/zh-cn_image_0000002778934781.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=C0D0BED404AC079BD7A00DCAFB9D75A1AA0B435489EFE6C8898E589B8A9E1C34) |
| AECH_DEVELOPER_DEFINED_ICON = 47 | 圆形自定义光标 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/3d/v3/MulsMJ0KT0qc6TavOJuZbw/zh-cn_image_0000002749335696.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=AEF197FC53D2EE48A87D4FFB81ED828E9FD03108276CAD889E318C4C91B95529) |
| SCREENRECORDER_CURSOR = 48 | 录屏光标 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/75/v3/7nhklbBHS-C4yo1PydoMQg/zh-cn_image_0000002749495580.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=4922F1A9608FB9A1ADA009AE5075D1CD89BE50680DB12CDEAF8D663285C64C4D) |
| LASER_CURSOR = 49 | 悬浮光标。手写笔进入空鼠模式时使用该光标，无法直接设置。 空鼠模式支持通过手写笔在空中转动来控制屏幕上虚拟光标的移动，并借助笔身按键实现上下翻页功能，用于演示PPT、隔空操作等场景。 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/67/v3/LXFQNuNWQGKQqlajEGU_MA/zh-cn_image_0000002779094637.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=109E8FB95E0809E078B754ECA573C1C1EAA0FEC44CC813351A04BBBA994A0152) |
| LASER_CURSOR_DOT = 50 | 点击光标。手写笔进入空鼠模式时使用该光标，无法直接设置。 空鼠模式支持通过手写笔在空中转动来控制屏幕上虚拟光标的移动，并借助笔身按键实现上下翻页功能，用于演示PPT、隔空操作等场景。 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/1f/v3/JWvC5QRaTD-epgZJtawHTA/zh-cn_image_0000002778934783.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=3C831CC938B1BB9DE1C6B0F5A9DBF4D11EA1FD1850030A8C3C3EA672453B20D2) |
| LASER_CURSOR_DOT_RED = 51 | 激光笔光标。手写笔进入空鼠模式时使用该光标，无法直接设置。 空鼠模式支持通过手写笔在空中转动来控制屏幕上虚拟光标的移动，并借助笔身按键实现上下翻页功能，用于演示PPT、隔空操作等场景。 | ![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/82/v3/-ek05gMXQlWafubOAEr7sQ/zh-cn_image_0000002749335698.png?HW-CC-KV=V1&HW-CC-Date=20261009T012717Z&HW-CC-Expire=86400&HW-CC-Sign=9FA071E24A6475C4790B2D1FFA4D1F21EFD4EB838B8A3851527B6EF6F989F070) |
| DEVELOPER_DEFINED_ICON = -100 | 自定义光标，开发者可使用OH_Input_SetCustomCursor设置自定义光标，不支持使用OH_Input_SetPointerStyle直接设置。 | 自定义光标样式，通过接口设置。 |
