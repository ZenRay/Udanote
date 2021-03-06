**目录**

[TOC]

## 课程1: 描述统计学

课程主题：

1. 数据类型
2. 常见统计学方法
3. 集中趋势和离散程度
4. 常见数据类型
5. 异常值处理
6. 图形化表达统计信息



数据：

* 定义：不同的信息片段

* 数据来源及其形式：从各个行业，各种仪器等都有可能得到数据。1）`Excel` 表格；2）文本；3）音视频；4）数据库；5）图片 等等

### 1.1 数据类型

数据主要分为 **定量数据** 和 **分类数据**。表现上存在差异：

1. 定量数据（**Quantitative Data**），是可以通过数据运算的数值数据。这类数据还可以继续分类，**连续型数据（Continuous Data）** 和 **离散型数据（Discrete Data）**
   1. 连续型数据，以比例为度量水平，难以获得其最小精度。所有的数学运算度可以在该类数据上使用。
   2. 离散型数据，以间隔为度量水平，其不会使用小数表示数据。
2. 分类数据（**Categorical Data**），是被标记一个的群体或被标记的一组数据集。根据[度量水平](https://en.wikipedia.org/wiki/Level_of_measurement)的不同可以该类数据还可以被继续分为，**分类定序（Categorical Ordinal）** 和 **分类定类（Categorical Nominal）**
   1. 分类定序数据，可以使用排名和顺序的数据。最重要的作用是表现层级，例如二元对立数据，多层级的“光谱”值
   2. 分类定类数据，不可以进行排序和排序的数据。可使用的数据运算，可以使用相等或者包含；不同进行数据算数运算

**注意⚠️：** 数据类型的重要性，体现在数据类型决定了数据分析的方式，以及用什么类型的图示表达数据

### 1.2 数据统计学表达

统计分析数据，可以从集中趋势（**center**）、离散程度（**Spread**）、形状（**Shape**）以及异常值（**Outliers**）

1. 集中趋势分析：

   1. 均值（**Mean**）：将所有值相加，然后除以数据集中值的数量。
   2. 中位数（**Median**）： 将数据集从小到大排序后，能够将数据集一分为二的值。需要注意计算会因为数据个数是奇数还是偶数个而存在差异
      * 奇数个观察值，直接使用中间的数字
      * 偶数个观测值，中位数是中间两个值的平均值。在计算的时候，使用 $\frac{x_{\frac{n}{2}}+x_{\frac{n}{2}+1}}{2}$ ，可以参考 [Median - Wikipedia](https://en.wikipedia.org/wiki/Median) 。需要注意使用 `percentile` 方法模拟计算中位数，会因为不同的 `linear interpolation` 方法不同存在差异，参考[Percentile - Wikipedia](https://en.wikipedia.org/wiki/Percentile) 以及[numpy.percentile](https://het.as.utexas.edu/HET/Software/Numpy/reference/generated/numpy.percentile.html) 
   3. 众数（**Mode**）：是一组数据中出现次数最多的数值，因此存在极端情况——可能有多个众数也可能一个也没有
      * 无众数情况：所有独特值的频数都是相同的
      * 多众数情况：某几个独特值的频数是最大且相同

   **注意⚠️：** 使用什么集中趋势分析和描述数据，很重要的是取决于数据集的形状和异常值情况



## 参考

1. 符号表达式（**Notation**）是数学语言的通用交流工具。它的作用是：1）传达数学相关想法，深层次来说可以表达数学及其相关的原理；2）简化文字等表达方式。例如[梯度提升\_Gradient Boosting](https://en.wikipedia.org/wiki/Gradient_boosting) 原理阐述
   1. $X, Y$ 与随机变量：随机变量（**Random Variable**）是指某些流程的可能去值的占位符，符号表达式中可以使用 $X$ 来进行表示对某个随机变量或者群组随机变量的表达，同样还可以使用 $Y, Z$ 等。举个例子，在电子表格中，随机变量是对应的列；而观察值是每个行
   2. 大小写与随机变量：可以使用大写符号表示随机变量，而随机变量下对应观测值使用小写符号。*⚠️需要注意，在实际情况下可能会使用大写表示全体因变量，而用小写表示单个的变量——这一点在机器学习等方面使用角度*。如下举例子：
      1. **$P(X \geq 20)$**：**一个人在我们网站上花费 20 分钟或更多时间的概率是多少**
      2. $x1 = 10, x2 = 20, x3 = 45, x4 = 12,x5 = 8$：**5 个人访问了我们的网站，第一个花费了 10 分钟，第二个花费了 20 分钟，第三个花了 45 分钟，第四个花了 12 分钟，第五个花了 8 分钟**
   3. 数学计算与符号表达式：使用符号表达式来表示数学计算方式，是其重要的作用——例如：$sum=x_1+x_2+x_3$，计算三个观察值的和；$sum=x_1+...+x_n$ ，计算 $n$ 个观察值的和；$\bar{x}=\frac{x_1+x_2+x_3}{n}$，计算三个观察值的平均值。在符号表达式中还有一类用于聚合（**Aggregation**）符号，表示的是将多个符号简化为少量符号表达的方式。聚合一般符号：$\sum$ 表示求和，$sum=\displaystyle{\sum_{i=1}^3x_i}=x_1+x_2+x_3$，同样求平均值可以聚合为 $\bar{x}=\displaystyle{\sum_{i=1}^nx_i}\times\frac{1}{n}=\frac{x_1+...+x_n}{n} $；$\Pi$ 表示计算乘积；$\int$ 表示计算积分