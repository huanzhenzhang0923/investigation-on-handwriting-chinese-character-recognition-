#**Investigation On Handwriting Chinese Character Recognition**#

## 1.传统方法
任务分类：
单字识别、多行输入
online character recognition
offline character recognition
结构识别法：笔画分析一综合法（ABS法）、笔画序列识别法、属性关系图法(ARG)与多边形近似轮廓法</br>
统计识别特征：变换特征、笔画密度特征(SDF）、笔画方向特征（S-DCD）、背景特征、细胞特征、方向线素特征</br>
行切割：对二值图像从上到下逐行扫描，同时计算每扫描行的像素，以获取图像的水平投影。利用文字行间空白间隔造成的水平投影空隙，即可以将各行文字分割开来</br>
行切割的问题：在图像输入时，有时会出现纸张倾斜，造成文字行的倾斜。少量的倾斜对行切割以及后面的字切割和识别影响都不大。但倾斜严重时，相邻两行文字图像的水平投影可能互相重叠，使它们之间的空白间隙被填满而无法实现行切割</br>
字切割：字切割的作用是从行切割后得到的文字图像行中将单个汉字的图像分割出来，它利用字与字之间的空白间隔在图像行垂直投影上形成的空白间隙，将单个汉字的图像切割出来的</br>



## 2.数据集以及表现优异的模型
CASIA-HWDB</br>
[基于Tensorflow的单字识别](https://blog.csdn.net/zchang81/article/details/77085165)


## 3.基于深度学习的手写体识别

