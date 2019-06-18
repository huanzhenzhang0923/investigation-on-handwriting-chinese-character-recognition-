#**Investigation On Handwriting Chinese Character Recognition**

## 1.传统方法
任务分类：
单字识别、多行输入
online character recognition
offline character recognition</br>
结构识别法：笔画分析一综合法（ABS法）、笔画序列识别法、属性关系图法(ARG)与多边形近似轮廓法</br>
统计识别特征：变换特征、笔画密度特征(SDF）、笔画方向特征（S-DCD）、背景特征、细胞特征、方向线素特征</br>
行切割：对二值图像从上到下逐行扫描，同时计算每扫描行的像素，以获取图像的水平投影。利用文字行间空白间隔造成的水平投影空隙，即可以将各行文字分割开来</br>
行切割的问题：在图像输入时，有时会出现纸张倾斜，造成文字行的倾斜。少量的倾斜对行切割以及后面的字切割和识别影响都不大。但倾斜严重时，相邻两行文字图像的水平投影可能互相重叠，使它们之间的空白间隙被填满而无法实现行切割</br>
字切割：字切割的作用是从行切割后得到的文字图像行中将单个汉字的图像分割出来，它利用字与字之间的空白间隔在图像行垂直投影上形成的空白间隙，将单个汉字的图像切割出来的</br>
字切割的问题：汉字中有相当数量的由左、右两部分构成的二根字和由左、中、右三部分组成的三根字。二根字有：八、北、非”等；三根字也不少，如“川、排、衍”等。这些字的图像垂直投影在一个单字内部也会出现空白间隙，因而单纯使用垂直投影空白间隙切分单字的切割算法会产生误分</br>
单字识别中的匹配判决:是把待识汉字的特征和字典中的标准特征逐一比较，按照特征之间的距离把某一个标准特征所代表的汉字判定为识别后输出的汉字。</br>
“拒识字”:若特征距离虽然是最小、但其绝对值大于规定值的标准特征对应的汉字，则判决为“拒识字”</br>
词条匹配:利用汉语上下文关系来校验字符串是否合乎语法的方法之一。如双字词模式匹配，需要建立双字词库。除双字词外，还可以利用三字词、四字词等，但词条字数越多，搜索匹配越复杂，目前已有的汉字OCR很少采用。</br>

## 2.数据集以及表现优异的模型
CASIA-HWDB</br>
[基于Tensorflow的单字识别](https://blog.csdn.net/zchang81/article/details/77085165)


## 3.基于深度学习的手写体识别
###**端到端不定长文字识别**
</br>两大主流技术：CRNN OCR和attention OCR</br>
**CRNN**</br>
![CRNN](https://img2018.cnblogs.com/blog/1093303/201901/1093303-20190129201843455-243108334.png)
<br>
网络结构包含三部分，从下到上依次为：
1.卷积层，使用CNN，作用是从输入图像中提取特征序列;<br/>
2.循环层，使用RNN，作用是预测从卷积层获取的特征序列的标签（真实值）分布;</br>
3.转录层，使用CTC，作用是把从循环层获取的标签分布通过去重整合等操作转换成最终的识别结果;</br>
