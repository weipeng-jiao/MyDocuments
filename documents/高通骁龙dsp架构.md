![高通logo](C:\Users\kaipule\Desktop\高通骁龙DSP\image\高通logo.png)

[TOC]

## 一、 Qualcomm®Snapdragon™处理器
### 1. Snapdragon™处理器系列

Qualcomm Technologies，Inc. (QTI) 是一家无线电通信技术研发和芯片技术解决方案提供商，旗下主要产品有：

```
（1）调制解调器及射频系统Snapdragon™ X系列处理器
（2）移动终端平台Snapdragon™ SoC处理器
```

高通的Snapdragon™ SoC (System on Chip) 处理器广泛应用于智能手机、平板电脑和笔记本电脑等移动终端，其发展大致如下：

<img src="C:\Users\kaipule\Desktop\高通骁龙DSP\image\高通系列.png" width = "70%"   height = "70%"  alt="图片名称" align=center />

Snapdragon™ (骁龙) 处理器系列在发展过程中，有两套命名标准:

```
（1）给消费者看的命名标准：骁龙命名 (骁龙xxx)，代表了芯片的定位。
（2）给内部人员看的命名标准：内部代码命名 (MSM xxxx,SDM xxx,SM xxxx)，代表了处理器实际的工作性能。
```
#### (1). 骁龙命名

<img src="C:\Users\kaipule\Desktop\高通骁龙DSP\image\消费者命名.png" alt="消费者命名" style="zoom:80%;" />

 ```
   骁龙200系列已停产。
   骁龙400系列是低端处理器。
   骁龙600/700系列是中端处理器。
   骁龙800系列是高端处理器。
 ```

  

#### (2). 内部代码命名

早期骁龙处理器内部代码命名为MSM xxxx命名和APQ xxxx命名，其中MSM (Mobile Station Modem) 表示集成了通讯基带的手机处理器，APQ (Application Processor Qualcomm) 表示没有集成通讯基带的手机处理器。

<img src="C:\Users\kaipule\Desktop\高通骁龙DSP\image\内部代码.png" alt="内部代码" style="zoom:80%;" />

```
MSM/APQ命名规则：
第一位数字表示处理器cpu配置：6、7、8表示含CPU、soc基本上第一位数字全是8。
第二位数字表示支持的网络制式：0表示没有基带，2表示联通网络，6表示电信网络，9表示全网通。
第三位和第四位数字表示芯片代数：数字越大，芯片性能越好。
```

在2017年以后，处理器MSM xxxx命名和APQ xxxx命名开始停用，开始使用SDM xxx命名。而在2019年以后SDM xxx命名逐渐停用，开始使用为SM xxxx命名。

```
SDM命名规则：与骁龙命名序号一致
骁龙439(SDM439)，骁龙450(SDM450)，骁龙630(SDM630)，骁龙660(SDM660)
骁龙670(SDM670)，骁龙710(SDM710)，骁龙712(SDM712)，骁龙845(SDM845)
SM命名规则：暂未公开
骁龙460(SM4250-AA)，骁龙662(SM6115)，骁龙665(SM6125)，骁龙675(SM6150)
骁龙720G(SM7125)，骁龙765G(SM7250-AB)骁龙855(SM8150)，骁龙865(SM8250)
```



### 2. Snapdragon™处理器组成

<img src="C:\Users\kaipule\Desktop\高通骁龙DSP\image\骁龙865.png" alt="骁龙865" style="zoom: 67%;" />



常见的Snapdragon™处理器主要由 CPU (中央处理器) 、GPU (图形处理器)、DSP (数字信号处理器)、ISP (图像信号处理器)、Memory (内存) 和 Connectivity (连接器) 等主要模块组成，除此之外还有 Sensing Hub (传感器中枢)、Security Processor (安全处理器）、Location (定位) 等辅助模块。

Kryo™ CPU：

```
Kryo™ CPU基于ARM架构，经历了ARM的3代架构更迭，分别是：ARMv6、ARMv7（Krait™）、ARMv8（Kryo™），Krait™和Kryo™是高通基于ARM指令集架构授权的兼容性版本。
Kryo™ CPU由多个ARM核心组成，核心按类型一般分为两类：
（1）Gold大核心：高性能核心，一般都是基于ARM公版定制的核心，如：
	Kryo™485 Gold@2.84Ghz X 1
	Kryo™485 Gold@2.42Ghz X 3
（2）Silver小核心：低功耗核心，一般都是基于ARM公版修改的核心，如：
	Kryo™485 Silver@1.8Ghz（Cortex-A55）X 4
```

Adreno™ GPU

```
Adreno™ GPU基于统一渲染架构（Unified Shader Model），用于图形处理、视觉处理和支持GPGPU任务处理。
API支持：Vulkan、OpenGLES、OpenVG、OpenCL、OpenGL、Direct3D。
```

Hexagon™ DSP：

```
Hexagon™ DSP作为Snapdragon™处理器的AI引擎具有低功耗和高性能计算的特性，利用异构计算支持始终在线任务，如音频处理、传感器中枢和基带通信等任务。可以实现将计算密集任务从CPU转移到DSP中，进行低功耗计算处理。
```

Spectra™ ISP：

```
Spectra™ ISP具有高效的原始数据（Raw Bayer Data）传输和预处理功能，可实现自动对焦、自动曝光、自动白平衡等功能，能够与Adreno™ GPU和Hexagon™ DSP协作处理图像。支持下一代计算机视觉和其他使用情景，提升生物识别能力和高分辨率3D深度感测技术。
```

Memory

```
片外存储：
（1）LPDDR（Low Power Double Data Rate SDRAM）低功耗双倍数据速率内存：
		又称mDDR（Mobile DDR SDRM），是美国JEDEC固态协会面向低功耗内存制定的通信标准。主要面向移动终端，具有功耗低、体积小等特点。
片内存储：
（1）Cache 缓存：L1 L2
（2）TCM（Tightly Coupled Memories）紧耦合内存：
	-属于OnChip Memory，TCM使用物理地址，对TCM的写访问，受到MMU内部保护信息的控制。向 TCM 中的内存位置写入时，不会发生任何外部写入。
	-TCM 用于向处理器提供低延迟内存，它没有高速缓存特有的不可预测性。可以使用 TCM 来存放重要例程，如可预见的实时处理（中断处理）、时间可预见（加密算法）、避免cache分析（加密算法）、要求高性能的代码（编解码功能）的例程或者极需要避免高速缓存不确定性的实时任务。此外，可以使用 TCM 来保存暂时寄存器数据、局部属性不适合高速缓存的数据类型，以及中断堆栈等重要数据结构。
```

Connectivity

```
（1）X系列基带：支持LTE FDD, LTE TDD including CBRS support, LAA, LTE Broadcast, WCDMA (DB-DC-HSDPA, DC-HSUPA), TD-SCDMA, CDMA 1x, EV-DO, GSM/EDGE多种无线传输协议。
（2）FastConnect 6900移动连接系统:支持Wi-Fi 6、Wi-Fi 6E、4K QAM、蓝牙5.2、蓝牙双天线。
```

![SM8150-2](C:\Users\kaipule\Desktop\高通骁龙DSP\image\SM8150-2.PNG)



```

```







<img src="C:\Users\kaipule\Desktop\高通骁龙DSP\image\680dsp.jpg" alt="680dsp" style="zoom:80%;" />





## 二、 Hexagon™ DSP

### 1. Hexagon™ DSP组成

Hexagon™ 是高通公司数字信号处理器 (DSP) 产品系列的品牌名称，Hexagon™ DSP和Kryo™ CPU、Adreno™ GPU一起构成Snapdragon™ SOC 异构计算铁三角，其基本特点有：

```
（1）DSP相比CPU可实现高性能计算和高能效（省电）。
（2）用于卸载CPU任务，利用异构计算支持实时在线任务。
（3）音频任务：在无延迟、无失真的情况下流式传输音频，消除背景噪声。
（4）视觉任务：文本识别、对象识别、图像增强和图像内的面部识别。
```

Hexagon™ 也称为 QDSP6，代表“第六代数字信号处理器”，Hexagon (QDSP6) 和 pre-Hexagon (QDSP5) 内核都用于现代 Qualcomm SoC，QDSP5 主要用于低端产品。QDSP6架构发布了六个版本：

```
V1 (2006), V2 (2007–2008), V3 (2009), V4 (2010–2011), V5 (2013-2015)，V6 (2016-now)。
```

Hexagon™ 共有4个单独的DSP，每个DSP用于特定的功能，分别是：aDSP（audio DSP）、cDSP（compute DSP）、mDSP （modem DSP）、sDSP（sensor DSP），在不同系列的骁龙处理器中Hexagon™ DSPs 数量不同。

```
（1）aDSP：音频处理DSP，主要用于低功耗的音频处理，使音频在任何时候都能在最低功耗处理，可在移动端休眠时不用唤醒CPU直接进行音频传输。（2）cDSP：通用计算DSP，主要协助CPU进行计算密集型任务处理。相比较CPU的高功耗、高主频，虽然cDSP主频低，但具有低功耗、并行程度高的优点，很适合将CPU端易于并行的计算密集型任务加载到cDSP上计算。
（3）mDSP：基带处理DSP，mDSP主要协助Modem的信号调制调节，将编码译码等计算密集度高的任务从Modem加载到mDSP上处理。骁龙用于无线电信号处理的调制调解器Modem分为片内集成式和外挂式，一般4G基带基础在SOC中，5G基带大部分外挂SOC。
（4）sDSP：传感器处理DSP，又名SLPI（Sensorlow power island）低功率岛，用于代替旧的Sensor Hub，用来为始终开启的传感器提供低功耗、更精确的处理。
```

### 2. Hexagon™ cDSP历史

在Hexagon™早期版本，Hexagon™ 只有aDSP、mDSP和sDSP，由aDSP负责Audio/Voice 和 Compute application模块。在SDM820（Hexagon™ 680）开始，aDSP内部集成了HVX（Hexagon Vector eXtension）矢量处理单元。相比较使用ARM 的 NEON 优化 ，使用HVX 向量化进行图像处理，性能能够提升1~3倍，功耗可降低到原来的1/8~1/4。在SDM660（Hexagon™ 680）开始，原先的aDSP按功能拆分成了aDSP和cDSP，HVX 矢量处理单元也开始加载到cDSP上。

<img src="C:\Users\kaipule\Desktop\高通骁龙DSP\image\cDSP.PNG" style="zoom: 50%;" />

为了增强图像处理能力，SDM845添加了HCP（Hexagon CoProcessor）视觉和成像硬件加速器，用于卸载和加速Hexagon软件算法。随着AI领域应用的涌现和需求，SM8150（Hexagon™ 690）在cDSP外部新添了一个单独的硬件加速器 HTA（Hexagon Tensor Accelerator），协助cDSP面向定点DCNN深度卷积神经网络模型运算处理。到SM8350（Hexagon™ 780），cDSP芯片内部封装了一块专门用于AI MAC计算的协处理器 HMX（Hexagon Matrix eXtension)，添加了 HMX 之后的cDSP芯片更名为HTP（Hexagon Tensor Processor）。

| Snapdragon™ | Hexagon™ | Micro-architecture | HVX  | HCP  | HTA  | HXM  |
| :---------: | :------: | :----------------: | :--: | :--: | :--: | :--: |
|   SM8350    |   780    |        v68         |  √   |  x   |  x   |  √   |
|   SM8250    |   698    |        v66         |  √   |  √   |  √   |  x   |
|   SM8150    |   690    |        v66         |  √   |  √   |  √   |  x   |
|   SDM845    |   685    |        v65         |  √   |  √   |  x   |  x   |
|   SDM660    |   680    |        v60         |  √   |  x   |  x   |  x   |
|   SDM820    |   680    |        v62         |  x   |  x   |  x   |  x   |

当前高通推出了骁龙人工智能引擎 (Snapdragon AIE)，AIE由硬件和软件两大部分组成：

```
硬件方面：主要采用了异构运算，内部包含Hexagon DSP、Adreno GPU 和 Kryo CPU 的人工智能优化组合。
软件工具和库：包含了骁龙神经处理 SDK、 Android NN 和 Hexagon NN 等。
```

<img src="https://raw.githubusercontent.com/weipeng-jiao/MyImages/master/img/%E6%80%BB%E4%BD%93%E6%A1%86%E6%9E%B6.png" alt="总体框架" style="zoom:50%;" />

当前Hexagon DSP可用户可通过Hexagon DSP SDK对cDSP的标量单元和矢量单元编程开发，张量单元则是通过骁龙神经处理SDK调库使用。![软件架构](https://raw.githubusercontent.com/weipeng-jiao/MyDocuments/master/img/%E8%BD%AF%E4%BB%B6%E6%9E%B6%E6%9E%84.png)

### 3. Hexagon™ cDSP架构






## 三、 HVX™ 指令集

## 四、 Qualcomm®Snapdragon™ SDK
​			

CPU和DSP之间的通信通过共享内存和中断来完成的，对DSP的每次调用开销可以达到几毫秒。因此尽量避免调用它来处理一些琐碎的小任务，代替的最好将大型任务交给DSP来做。



参考资料：
https://blog.csdn.net/cookie_plus/article/details/117663705

https://blog.csdn.net/weixin_43326587/article/details/107918002

http://yuenshome.space/timeline/2019-04/snpe/