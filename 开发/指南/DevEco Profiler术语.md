# DevEco Profiler术语

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-profiler-glossary

## 异步栈缝合

在异步回栈时，可单击工具控制栏中的![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/01/v3/8gQJy_rVTCuQkqNq6ZVw1g/zh-cn_image_0000002731382645.png?HW-CC-KV=V1&HW-CC-Date=20261009T012823Z&HW-CC-Expire=86400&HW-CC-Sign=20A24BB82FBD9FA31085C0208A808F909F7B0DD39B00C156502F3E2B02C014DE)按钮，配置异步栈嵌套层数和异步回栈层数。
 
如下图中的start_malloc_xxx_work异步调用malloc_xxx_work，当开关未开启时，仅能回malloc_xxx_work栈帧；当开关开启后，支持回malloc_xxx_work栈帧和start_malloc_xxx_work栈帧。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/c3/v3/KauwHhTAQGa0QcpsHpziDQ/zh-cn_image_0000002701823342.png?HW-CC-KV=V1&HW-CC-Date=20261009T012823Z&HW-CC-Expire=86400&HW-CC-Sign=441670A7CC137487E57C94824B3E240CC50A6C2331D721C948C4E78558324D6B)
