[TOC]

![opencv-logo](https://raw.githubusercontent.com/weipeng-jiao/MyImages/master/img/opencv-logo.png)

## 一、OpenCV简介



### 1. OpenCV的定义
```
 OpenCV的英文全称是Open Source Computer Vision Library。它是一个开源的计算机视觉库，它由一系列 C 函数和少量 C++ 类构成，实现了图像处理和计算机视觉方面的很多通用算法。
```

### 2. OpenCV的特点

    （1）OpenCV采用C/C++语言编写，可以运行在Linux/Windows/Mac等操作系统上。
    （2）OpenCV提供了Python、Ruby、MATLAB以及其他语言的接口。
    （3）它采用优化的C代码编写，能够充分利用多核处理器的优势。
    （4）具有良好的可移植性。

### 3. OpenCV的设计目标

```
执行速度尽量快，主要关注实时应用。如果是希望在Intel平台上得到更快的处理速度，可以购买Intel的高性能多媒体函数库IPP(Integrated Performance Primitives)。IPP库包含许多从底层优化的函数，这些函数涵盖多个应用领域。如果系统已经安装了IPP库，OpenCV会在运行时自动使用相应的IPP库。
```

### 4. OpenCV的应用领域
```
  (1)人机互动       
  (2)物体识别         
  (3)图象分割    
  (4)人脸识别       
  (5)动作识别   
  (6)运动跟踪      
  (7)机器人       
  (8)运动分析     
  (9)机器视觉      
  (10)结构分析
```

### 5. OpenCV的组成模块

![模块](C:\Users\kaipule\Desktop\计算机视觉\opencv\image\模块.png)

**常用模块：提供经典的图像处理算法、计算机视觉算法应用和读写显示操作**

```
基础模块：用于基础的图像处理操作
1.core：核心模块，主要包含了OpenCV中最基本的结构（矩阵，点线和形状等），以及相关的基础运算/操作。
2.imgproc：图像处理模块，包含和图像相关的基础功能（图像滤波、图像的几何变换、平滑等），以及一些衍生的高级功能（阈值分割、形态学处理、边缘检测、目标检测、运动分析和对象跟踪等）。
3.highgui：图像GUI/IO模块，提供了图像显示窗口的生成和控制，图像/视频文件的IO等函数。

高级模块：高层次的图像处理操作计算机视觉算法应用
4.features2d模块：图像二维特征相关模块，用于图像特征点提取以及特征点匹配等功能，nonfree模块包含了受专利保护的算法，如SIFT和SURF。
5.objdetect模块：目标检测模块，实现了一些目标检测的功能，经典的基于Haar、LBP特征的人脸检测，基于HOG的行人、汽车等目标检测，分类器使用Cascade Classification(级联分类)和Latent SVM等。
6.stitching模块：图像拼接模块，主要包含特征点寻找与匹配图像、估计旋转、自动校准、接缝估计等图像拼接技术。
7.FLANN模块：(Fast Library for Approximate Nearest Neighbors)，包含快速近似最近邻搜索FLANN 和聚类Clustering算法，用于在多维空间进行聚类和检索，经常和关键点匹配搭配使用。
8.ml模块：机器学习模块，包含一些经典的机器学习算法，如支持向量机和随机森林等。
9.photo模块：计算摄影模块，包含图像修复和图像去噪两部分。
10.video模块：视频分析模块，主要包含运动估计、背景分离、对象跟踪等视频处理相关内容。
11.videoio：视频读写模块，主要负责视频文件的读取和写入。
12.calib3d模块：3d视觉模块，该模块由相机校准（calibration）和三维重建（3d）两个部分组成，主要用于相机标定与三维视觉等，包含了基本的多视角几何算法，单个立体摄像头标定，物体姿态估计，立体相似性算法，三维重建等。
13.G-API模块：算法加速模块，对图像处理算法做了加速处理，不属于OpenCV的功能模块，包含了超高效的图像处理pipeline引擎。
```

**扩展模块：对于具有专利的算法（如SURF）以及一些还没有稳定的前沿算法，OpenCV会将其置于扩展模块中，这些扩展模块包含在opencv_contrib代码库中：**

```
opencv_contrib的模块及其功能说明如下：
alphamat：Alpha Matting信息流算法。
aruco：增强现实标记算法。
barcode：条形码检测与解码方法。
bgsegm：增强背景-前景分割算法。
bioinspired：仿生学视觉模型和衍生工具。
ccalib：用于三维重建的自定义校准模式。
cudaarithm：CUDA矩阵运算。
cudabgsegm：CUDA背景分割。
cudacodec：CUDA视频编解码。
cudafeatures2d：CUDA特征检测与描述。
cudafilters：CUDA图像滤波。
cudaimgproc：CUDA图像处理。
cudalegacy：CUDA传统支持。
cudaobjdetect：CUDA目标检测。
cudaoptflow：CUDA光流算法。
cudastereo：CUDA立体匹配。
cudawarping：CUDA图像扭曲。
cudev：CUDA设备层。
cvv：计算机视觉程序交互式可视化调试的GUI。
datasets：用于处理不同数据集的框架。
dnn_objdetect：基于DNN的目标检测。
dnn_superres：基于DNN的超分。
dpm：基于可变形零件的模型。
face：人脸分析。
freetype：使用freetype/harfbuzz绘制UTF-8字符串。
fuzzy：基于模糊数学的图像处理。
hdf：分层数据格式I/O例程。
hfs：基于层次特征选择的图像分割方法。
img_hash：该模块提供了不同的图像哈希算法的实现。
intensity_transform：该模块提供了用于调整图像对比度的强度变换算法的实现。
julia：OpenCV Julia绑定。
line_descriptor：用于从图像中提取线条的二进制描述符。
mcc：Macbeth图表模块。
optflow：光流算法。
ovis：OGRE三维可视化器。
phase_unwrapping：相位展开API。
plot：Mat数据绘制函数。
quality：图像质量分析API。
rapid：基于轮廓的三维目标跟踪。
reg：图像配准。
rgbd：RGB深度处理。
saliency：显著性API。
sfm：运动结构分析。
shape：形状距离与匹配。
stereo：立体匹配算法。
structured_light：结构光API。
superres：超分模块。
surface_matching：曲面匹配。
text：场景文字检测与识别。
tracking：追踪API。
videostab：视频稳定。
viz：三维可视化器。
wechat_qrcode：微信二维码检测器，用于检测和解析二维码。
xfeatures2d：features2d扩展模块。
ximgproc：imgproc扩展模块。
xobjdetect：objdetect扩展模块。
xphoto：photo扩展模块。
```

### 6. OpenCV的使用安装

#### (1). C++版本

```

```



#### (2). Python版本
使用pip安装Opencv

```
pip install opencv-contrib-python
```

如果pip原始源下载慢的话可以考虑使用国内源:
```
pip3 install opencv-contrib-python -i https://pypi.tuna.tsinghua.edu.cn/simple
```

pip提供的opencv的包的类型有四种:

```
opencv-python: 只包含opencv库的主要模块，一般不推荐安装。
opencv-contrib-python: 包含主要模块和contrib模块, 功能基本完整, 推荐安装。 
opencv-python-headless: 和opencv-python一样, 但是没有GUI功能, 无外设系统可用。
opencv-contrib-python-headless: 和opencv-contrib-python一样但是没有GUI功能，无外设系统可用。
```
一般选择安装 opencv-contrib-python，不要同时安装 opencv-python 和 opencv-contrib-python
## 二、OpenCV的IO操作
### 1. 图像数据类型
![图像方向](C:\Users\kaipule\Desktop\计算机视觉\opencv\image\图像方向.png)

opencv中的图像类型为 Mat 类型：Mat 是一个类，由两个数据部分构成，矩阵头（包含矩阵尺寸，存储方法，存储地址等)和一个指向存储所有像素值的矩阵的指针。

#### (1). 成员变量：

```
int cv::Mat::cols      //返回矩阵的列数 
int cv::Mat::rows      // 返回矩阵行数 
uchar* cv::Mat::data   // 指向矩阵的数据单元的指针 
int cv::Mat::dims      // 返回矩阵维度，该维度≥2 
MatSize cv::Mat::size  // 返回矩阵大小
```
#### (2). 成员函数：


```
mat_name.depth()		//获取图像位深度
mat_name.channnels()	//获取矩阵的通道数
mat_name.type()			//获取存储元素的数据类型
```

#### (3). Mat对象

```
Mat Matrix_name(行数，列数，存储元素的数据类型，每个矩阵点的通道数)
常见的Mat对象初始化：
Mat Matrix_name()：没有参数的默认构造函数，主要用来接受读取的图像数据。
Mat Matrix_name(int rows, int cols, int type)：表示二维数组的行数和列数，以及数组的类型(用于存储数据)。
Mat Matrix_name(int rows, int cols, int type, Scalar s)：包括前一个的参数，此构造函数还接受Scalar类的一个对象作为参数。
Mat Matrix_name(Size size, int type)：一个表示矩阵大小的对象（rows，cols）和一个表示用于存储数据的数组类型的整数。
Mat Matrix_name(Size size, int type, Scalar s)：包括前一个的参数，此构造函数还接受Scalar类的一个对象作为参数。
Mat Matrix_name(long addr)：只用一个long类型作为参数。
Mat Matrix_name(Mat m, Range rowRange)：接受另一个矩阵的对象和创建新矩阵的行的范围。
Mat Matrix_name(Mat m, Range rowRange, Range colRange)：包括前一个的参数和创建新矩阵的列的范围。
Mat Matrix_name(Mat m, Rect roi)：接受两个对象，一个表示另一个矩阵，另一个表示兴趣区域。
特殊的Mat对象初始化：
Mat ones()：每个像素的第一个通道为1，其余通道为0。
Mat zeros()：每个像素的每个通道都为0。
```
#### (4). Mat数据类型

```
CV_[位数][类型前缀]C[通道数]
1.位数表示8bite,16bites,32bites,64bites等比特数，例如8位表示CV_8
2.类型前缀分为：S|U|F
		S--代表---signed int---有符号整形
        U--代表--unsigned int--无符号整形
        F--代表--float---------单精度浮点型
3.通道数表示图像的通道数,比如:
     	灰度图片--grayImg---是--单通道图像
     	RGB彩色图像---------是--3通道图像
     	带Alphf通道的RGB图像--是--4通道图像
举例：CV_16UC1表示16位单通道灰度图，CV_24UC3表示3通道RGB彩色图，每个通道是8位
```

### 2. 图像数据IO

#### (1). 图像读取：**imread**

```
Mat img=imread(“读取的图像路径”,参数)
参数1 IMREAD_UNCHANGED (加载原图)，可用-1表示。
参数2 IMREAD_GRAYSCALE (灰度图像)，可用0表示。
参数3 IMREAD_COLOR (读入彩色图像)，可用1表示。
```

#### (2). 图像窗口：**namedWindow、destroyAllWindows、destroyWindows**

```
窗口创建：
namedWindow("窗口标题",参数)
参数1 WINDOW_AUTOSIZE（默认形式:窗口不能调节大小）
参数2 WINDOW_AUTOSIZE（窗口可以调节大小）
窗口销毁：
destroyAllWindows() //删除所有窗口
destroyWindows("窗口标题") //删除指定的窗口
```

#### (3). 图像显示：**imshow、waitKey** 

```
imshow("窗口标题"，"图像名称")
waitKey(delay)//键盘绑定函数，参数delay表示等待毫秒整数，返回值为ASCII值。
参数delay<0表示等待键盘单击。
参数delay=0，则表示无限期的等待键盘输入。
参数delay>0表示等待delay毫秒。
```

#### (4). 图像保存：imwrite

```
imwrite("保存的图像路径"，Mat对象)
```

#### (5). 实例

### 3. 图像操作


参考资料：

https://zhuanlan.zhihu.com/p/456174380
https://www.zhihu.com/question/436567194/answer/2573636801
https://blog.csdn.net/xiaofeilong321/article/details/8841125