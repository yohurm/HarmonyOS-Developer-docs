# DevEco Profiler术语

更新时间：2026-08-29 09:41:34

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-profiler-glossary

## 异步栈缝合

在异步回栈时，可单击工具控制栏中的![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/08/v3/_cKRKMpCQCO4fn7xCGf2og/zh-cn_image_0000002731382645.png?HW-CC-KV=V1&HW-CC-Date=20260911T072348Z&HW-CC-Expire=86400&HW-CC-Sign=922173E54FAF3E84C77FEBD171BFFD2936202132BD6C72076E84084B07AF8518)按钮，配置异步栈嵌套层数和异步回栈层数。
 
如下图中的start_malloc_xxx_work异步调用malloc_xxx_work，当开关未开启时，仅能回malloc_xxx_work栈帧；当开关开启后，支持回malloc_xxx_work栈帧和start_malloc_xxx_work栈帧。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/3d/v3/Xk_w4dHjS-yvRzHQdORzbg/zh-cn_image_0000002701823342.png?HW-CC-KV=V1&HW-CC-Date=20260911T072348Z&HW-CC-Expire=86400&HW-CC-Sign=B5044E5157425467848F681057AD8CF2DAD5AB567EB718C6B71E3CAD32B9A76B)
