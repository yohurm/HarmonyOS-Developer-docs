# Frame分析

更新时间：2026-10-08 09:38:49

来源：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-insight-session-frame

## 功能介绍

开发应用或元服务过程中，如果发现有表单滑动不顺畅、页面交互延迟、动效不流畅等卡顿现象时，可以使用DevEco Profiler提供的Frame场景分析能力，录制卡顿过程中的关键数据并进行分析，从而识别出导致卡顿丢帧的原因。
 
 
Frame模板支持的泳道包括：Frame、Callstack、CPU Core、Process。本文介绍Frame、CPU Core、Process泳道，Callstack泳道的介绍请参考[基础耗时分析：Time分析](https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-hmos-insight-session-time)。
 
> [!NOTE]
> 卡顿丢帧分析前，需创建Frame分析任务并录制相关数据，操作方法可参考 性能问题定位：深度录制 ，或在会话区点击 图标，导入历史数据。

 

## 查看GPU使用情况

**Frame**泳道显示当前设备的GPU的使用率，将其展开，子泳道显示渲染服务（Render Service）侧帧数据和App侧帧数据。
 
在带有**RS Frame**和**App Frame**标签的泳道中，正常完成渲染的帧显示为绿色，出现卡顿的帧显示为红色。
> [!NOTE]
> 一帧的绘制，一般需要由App侧提交渲染到Render Service侧，然后Render Service侧再提交给硬件进行合成渲染，因此App侧的帧和Render Service侧的帧存在关联的情况。并且可能多个APP侧的帧/同一APP侧的多个帧提交到同一个Render Service侧帧上，出现帧之间的一对多的关联情况。 一帧绘制的期望耗时，与fps的大小有关，一般情况下fps为60，对应的Vsync周期为16.6ms，即App侧/Render Service侧的帧耗时，一般需要在16.6ms以内。App侧帧/Render Service侧帧判断卡顿的标准为帧的实际结束时间晚于帧的期望结束时间。

 
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/f9/v3/6sryLeK7RMOHLlVCo_omPQ/zh-cn_image_0000002749323896.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=D2DF31323356C285CF888F6AA8831F2A65B1BB15DAE6983825113D752E0D07C4)

 
 

## 查看指定时间段内所有进程的Frame数据统计信息
1. 在时间轴上拖拽鼠标选定要查看的时间段。
2. 框选**Frame**主泳道。窗口下方的**Statistics**区域中会以进程为维度对选定时间段内的Frame信息进行统计，包括卡顿率、卡顿次数、最大连续卡顿次数、最大卡顿耗时、平均卡顿耗时以及平均正常耗时等。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/65/v3/wlo-uu9VReqHoScvnSegDQ/zh-cn_image_0000002778922979.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=B04581BABDEE1937547C209A5D0872A12EC1C1C0DEDE7B49DE1E971B7A2863C0)

3. 点击**Statistics**列表中任一进程的跳转按钮，在**Frame List**区域将展现该进程对应的Frame列表。体现各帧的起始时间、总耗时、GPU耗时以及卡顿丢帧类型。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/db/v3/I2XQpYwASfSaWr9pyCpZ8w/zh-cn_image_0000002779082837.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=DD4A131F542B4F5101D7E903EBE94F5CFFD123DC9EAF44477A8F7D51CCCE6264)

4. 单击**Frame List**列表中任意一帧，右侧的**More**区域中会显示该帧更多关键信息。在获取该帧的预期起始时间、预期持续时间之外，您可以单击![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/bb/v3/Kt-WMrNVSBqLX9GmZXiKmw/zh-cn_image_0000002749323886.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=897B8C4397A967724B1DFB2658D2DF38572D030AB1094AAE0AB7800D33FEEABF)跳转至关联的切片。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/82/v3/DrKhTjdnRjmSRlNcNQOFwg/zh-cn_image_0000002749323900.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=4989AD24B270D5950BC607E88EB7157A44E3A4B970EC7C519D171AFD7563C427)

 
 

## 查看指定时间段内指定进程的Frame数据统计信息
1. 在时间轴上拖拽鼠标选定要查看的时间段。
2. 展开**Frame**主泳道，选择要观察的带**App Frame**或带**RS Frame**标签的子泳道。

  窗口下方的**Details**区域中会显示选定时间段内的RS帧统计信息列表，体现各帧的起始时间、总耗时、GPU耗时以及卡顿丢帧类型。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/67/v3/FES6D_qeTSOr1rqr3oiqiw/zh-cn_image_0000002749483776.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=66F42F40ECCDA7FFF6CFA53E65F5C5F0098C63303F78FBD27A122603D5CE1504)

3. 单击列表中任意一帧，右侧的**More**区域中会显示该帧更多关键信息。在获取该帧的预期起始时间、预期持续时间之外，您可以单击![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4f/v3/a5xmXJi4Tc-WZW2bGlRZaw/zh-cn_image_0000002749483778.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=875D2513A2E90AAFB1F114A2CEA80E6C74E7F27599B543ADAEBAA69A84CCA252)跳转至关联的切片。
 
 

## 查看指定Frame信息

展开**Frame**主泳道，选择带**App Frame**或带**RS Frame**标签的子泳道，该泳道图区域上方是耗时最长的非UI函数，下方是UI主线程泳道。将鼠标悬浮在任意帧上，会冒泡显示该帧的Jank信息。
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/a5/v3/AkBnZ1wPSueEb5b_fRiv-A/zh-cn_image_0000002778922973.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=7B589DF5C85CDCDA9640A0C26454DF0159542AA480D633010C43226A9F5F724E)

 
窗口下方的**Frame**区域中会显示选定帧的关键信息，如VSync编号、开始时间、App应用侧持续时间、App应用侧业务逻辑耗时、Render Service侧持续时间、GPU持续时间、总持续时间、卡顿丢帧类型以及可能出现卡顿的原因等。在带**App Frame**标签的子泳道中，**Non UI**区域中会显示非UI耗时最大的函数，如开始时间、结束时间、持续时间，函数名等。
 
> [!NOTE]
> 在选定观察对象后，DevEco Profiler会自动关联与其相关的切片，用箭头连接。 如果该帧是由于超出期望结束时间引起的，则显示两条线，对应期望开始时间（Expected Start）和期望结束时间（Expected End），用于关联分析同一时刻Trace或者函数采样信息。 卡顿丢帧类型（Jank Type）：No Jank（不卡顿）、AppDeadlineMissed（App侧的卡顿）、RenderDeadlineMissed（Render Service侧的卡顿）。

 
 

![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/87/v3/p26yVUEzTse9xQAov7rDpQ/zh-cn_image_0000002778922985.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=21C94FEB4901A5C6EE2DA8703F11BFBA80324C48333001E5904AFA2B4C117B38)

 

## 查看帧率统计信息
1. 展开**Frame**泳道，框选一段数据。
2. 带**App Frame**和**RS Frame**标签的子泳道会出现FPS标记，展示当前框选范围内的帧率统计信息。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/ab/v3/0X-2JztfRPewgYJQ3MPxpA/zh-cn_image_0000002778922991.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=A38894D14DEACE796B616C4427398E9F3BD545014519ADA687CBB98403DFFAE4)

3. 在带**RS Frame**标签的子泳道中打开**筛选出ArkWeb数据**开关，筛选过滤出包含ArkWeb帧的数据。

  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/59/v3/KFijr_2LTViwMD5UhvqIHQ/zh-cn_image_0000002779082831.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=4605D009A5359BBAE5A8A96E3289E2F2A63CA84B0235DBF3A53B70B220581245)

 
 

## 查看各CPU使用情况
1. **CPU Core**泳道显示当前选择调优应用或元服务的CPU的使用率，在泳道右侧![icon](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/4a/v3/gCPaHr8TRomOT-aBz3SMVA/zh-cn_image_0000002779082827.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=00EA08B8EB3600DE8807A93771D3BB184B55698E79E4B073E29ED3B72069EAF8)图标下拉列表中选择显示内容：
- **Slice and Frequency**：每个子泳道包含时间片和频率两部分，时间片显示占用该CPU核心的进程、线程。

2. **Usage and Frequency**：每个子泳道包含CPU核心使用率和频率两部分。

3. 将其展开，子泳道显示各CPU核心调度信息、各CPU核心频率信息以及各CPU核心使用率信息。
> [!NOTE]
> 将鼠标悬浮在某时间片上时，能够置灰非同进程时间片，通过此方法可以确定时间片的关联性。


  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/68/v3/N_0QH5mCSTuAwjDvTTQvuQ/zh-cn_image_0000002778922987.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=9FD8D4A1EB00296A406CAB7795BBF01CDB32F764B8931D9DA14C88EECB32CA3D)


4. 指定时间片，查看统计信息。
单击某个运行状态的时间片，可查询这个时间片的基本运行信息及调度时延信息。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/b/v3/ENFF172lREm0X412465pOA/zh-cn_image_0000002749323888.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=171E37C0AD00B4146730F985469A6E2D18E33780C50C368DDEB33DCA1D187CC0)


5. 框选多个时间片，则可查询多时间片的进程维度统计信息以及所有时间片的数据统计信息。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/89/v3/MMXU8qaISOygj66rUimJYA/zh-cn_image_0000002779082839.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=349109457B2A68291380870119BDBC3803A98DC8E99DC9577676F51020F60874)


6. 开启**查看完整调度链**后，点击CPU时间片泳道的节点可以查看某一个CPU运行线程的完整唤醒调度链。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/b2/v3/GU4iO91-TVavHy9Y5r2Whg/zh-cn_image_0000002778922989.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=22CF7D0D4504A3B5E356C2E234FE5057F07E819C3C3874799BBB539AA4B363DF)


  

  ## 查询进程详情

  进程泳道显示进程对各CPU核心的占用情况。展开进程泳道，显示进程下的线程列表以及线程的运行状态。

  
单击运行状态的时间片，显示线程在该片段的运行详情，包括起始时间、持续时长、运行状态、所属进程，支持跳转到上个或者下个线程运行状态，支持跳转到唤醒线程状态等。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/e7/v3/EVg2ajJjSxWQPGY7B8Rb_g/zh-cn_image_0000002749483774.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=F704DF1076C9D6CA322267F912470AB0A5B74EF89504E1B2FCECFB18078296BE)

- 框选Thread泳道中多个运行状态的时间片，可查看此时间段内的不同运行状态的线程的统计信息，包括总耗时时长、最大耗时、最小耗时、平均耗时、处于当前状态的线程数量以及线程中的中载和重载数据统计。
> [!NOTE]
> 中载、重载数据每100ms做一次统计，24ms < Running时长 ≤ 48ms 记为中载，Running时长大于48ms记为重载。


  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/58/v3/bjY26yRVQkW1OPce0Fz1UA/zh-cn_image_0000002778922975.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=2C5E3C49A32F9820246456E7D02E21316CFD86B96AEC9DD6C84866E38AEC5AA9)

- 框选应用进程Process主泳道，可查看此时间段内该进程下的线程并行度统计信息。并行度数据每100ms做一次统计，可以查看100ms内运行的总线程数量、各线程数并行的总时间和并行度。点选某一行，可以查看对应线程编号和运行时间段。
> [!NOTE]
> 并行度（Parallelism）取值范围是[1, cpu核数]，数值越小代表并行度越低。


  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/3b/v3/BuAJz-f0S8yXEW_swDvBxw/zh-cn_image_0000002749323898.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=19917E2774EA3AD5E48395C8DFAB176AC9B63C672FE78B2AFD6FCEE9B2527850)


 

## 查看Trace详情

当存在Trace任务时，可在对应的线程泳道查看到当前线程已触发的Trace任务层叠图。选择待查询的Trace。
 
- 点选泳道中的Trace片段，可查看单个Trace详情，包括名称、起始时间、持续时长、深度等。
> [!NOTE]
> 如果用户对线程进行了自定义打点，在此处亦可查看到对应的User Trace打点信息。 从所在线程名称可分辨当前Trace的类型，系统Trace对应的线程名称为“线程名+线程号”，User Trace对应的线程名称为“打点任务名”。


  
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/12/v3/LQfCidg6R6mSkBVc1I1xhA/zh-cn_image_0000002749483764.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=6D183D96AB5F7B558EAE47A50B5A18220FF8DB6E13A1EE681D295D8924629A4B)

- 框选多个Trace片段，可查看到Trace统计信息列表，包括Trace名称、此类Trace的总耗时、单个Trace的平均耗时、以及该时间段内该类Trace的触发次数等。
![](https://contentcenter-vali-drcn.dbankcdn.cn/pvt_2/DeveloperAlliance_scene_100_1/da/v3/BgpDkhp9R_ev4ZxLE0I9_g/zh-cn_image_0000002749323904.png?HW-CC-KV=V1&HW-CC-Date=20261009T012533Z&HW-CC-Expire=86400&HW-CC-Sign=B1B21DE278ECD15642F60F51CC689A739C4A8E8F8535E8C97AD669E38751255F)
