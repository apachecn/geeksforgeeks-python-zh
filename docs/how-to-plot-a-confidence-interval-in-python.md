# 如何用 Python 绘制置信区间？

> 原文:[https://www . geesforgeks . org/如何绘制 python 中的置信区间/](https://www.geeksforgeeks.org/how-to-plot-a-confidence-interval-in-python/)

置信区间是一种从观测数据的统计中计算出来的估计值，它给出了一个可能包含具有特定置信水平的总体参数的数值范围。

平均值的置信区间是总体平均值可能位于的一系列值。如果我对明天的天气做一个-100 度到+100 度之间的预测，我可以 100%确定这是正确的。然而，如果我把温度预测在 20.4 到 20.5 摄氏度之间，我就没那么自信了。注意随着间隔的减小，置信度是如何降低的。这同样适用于统计置信区间，但它们也依赖于其他因素。

一个 95%的置信区间，会告诉我，如果我们从我的总体中抽取无限数量的样本，计算每次的区间，那么在那些区间的 95%中，区间将包含真实的总体均值。因此，对于一个样本，我们可以计算样本平均值，并从中得出一个区间，该区间很可能包含真实的总体平均值。

![](img/8859fbd986183a0af2e06a95d9ec3006.png)

两条黑线下的区域显示了 95%的置信区间

置信区间是杰吉·内曼在 1937 年发表的一篇论文中提出的一个概念。置信区间有各种类型，最常用的有:均值的置信区间、中位数的置信区间、均值差的置信区间、比例的置信区间和比例差的置信区间。

让我们看看 Python 是如何做到这一点的。

## **计算 C .我使用 lineplot()** 给出了基础分布

在 Python 的数据可视化库 *Seaborn，*中提供的 [lineplot()](https://www.geeksforgeeks.org/seaborn-lineplot-method-in-python/) 功能最适合显示一段时间内的趋势，但是它也有助于绘制置信区间。

**语法:**

> SNS . line plot(x =无，y =无，色相=无，大小=无，样式=无，数据=无，调色板=无，色相 _ 顺序=无，色相 _ 范数=无，大小=无，大小 _ 顺序=无，大小 _ 范数=无，破折号=真，标记=无，样式 _ 顺序=无，单位=无，估计器= '平均值'，ci=95，n_boot=1000，排序=真，err_style= '波段'，err _ kws =无，图例= '简短'，ax =无，* * *
> 
> **参数:**
> 
> *   **x，y:** 输入数据变量；必须是数字。可以直接传递数据或引用数据中的列。
> *   **色调:**将产生不同颜色线条的分组变量。可以是分类的，也可以是数字的，尽管颜色映射在后一种情况下会有不同的表现。
> *   **样式:**分组变量，将产生具有不同破折号和/或标记的线条。可以有数字数据类型，但将始终被视为分类数据类型。
> *   **数据:**整齐的(“长格式”)数据帧，其中每一列是一个变量，每一行是一个观察值。
> *   **标记:**确定如何为不同级别的样式变量绘制标记的对象。
> *   **图例:**如何绘制图例。如果“简短”，数字“色调”和“大小”变量将以均匀间隔的值的样本表示。
> 
> **返回:**包含绘图的轴对象。

默认情况下，该图在 x 的每个值上聚合多个 y 值，并显示中心趋势的估计值和该估计值的置信区间。

**示例:**

## 蟒蛇 3

```py
# import libraries
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

# generate random data
np.random.seed(0)
x = np.random.randint(0, 30, 100)
y = x+np.random.normal(0, 1, 100)

# create lineplot
ax = sns.lineplot(x, y)
```

在上面的代码中，变量 x 将存储 100 个从 0(包括)到 30(不包括)的随机整数，变量 y 将存储 100 个来自高斯(正态)分布的样本，该分布以 0 为中心，分布/标准差为 1。 *NumPy* 运算通常是在一个元素接一个元素的基础上对数组对进行的。在最简单的情况下，两个数组必须具有完全相同的形状，如上例所示。最后，在 *seaborn* 库的帮助下，默认以 95%的置信区间创建*线图*。置信区间可以很容易地通过改变参数“ci”的值来改变，该值在[0，100]的范围内，这里我没有传递这个参数，因此它考虑默认值 95。

![](img/50757091b0fc176333be775c37a66637.png)

浅蓝色阴影表示该点周围的置信度。如果置信度较高，阴影线会更粗。

## **使用正则图()计算给定基础分布的 c . I .**

[seaborn.regplot()](https://www.geeksforgeeks.org/python-seaborn-regplot-method/) 有助于绘制数据和线性回归模型拟合。该功能还允许绘制置信区间。

**语法:**

> seaborn.regplot( x，y，data=None，x_estimator=None，x_bins=None，x_ci='ci '，散点=True，fit_reg=True，ci=95，n_boot=1000，单位=None，顺序=1，logistic=False，lowess=False，robust=False，logx=False，x_partial=None，y_partial=None，truncate=False，dropna=True，x_jitter=None，y_jitter=None，label=None，color=None，marker=
> 
> **参数:**部分主要参数描述如下:
> 
> *   **x，y:** 这些是输入变量。如果是字符串，这些应该与“数据”中的列名相对应。当熊猫对象被使用时，轴将被标上系列名称。
> *   **数据:**这是数据帧，其中每一列是一个变量，每一行是一个观察值。
> *   **下限:**(可选)该参数取布尔值。如果为“真”，则使用“统计模型”来估计非参数低限模型(局部加权线性回归)。
> *   **颜色:**(可选)应用于所有绘图元素的颜色。
> *   **标记:**(可选)用于散点图字形的标记。
> 
> **返回:**包含绘图的轴对象。

基本上，它在*散点图*中包含一条回归线，有助于看到两个变量之间的任何线性关系。下面的例子将展示如何使用它来绘制置信区间。

**示例:**

## 蟒蛇 3

```py
# import libraries
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

# create random data
np.random.seed(0)
x = np.random.randint(0, 10, 10)
y = x+np.random.normal(0, 1, 10)

# create regression plot
ax = sns.regplot(x, y, ci=80)
```

*regplot()* 函数的工作方式与 *lineplot()* 相同，默认情况下置信区间为 95%。通过改变参数“ci”的值，可以很容易地改变置信区间，该值在[0，100]的范围内。这里我传递了 ci=80，这意味着不是默认的 95%置信区间，而是绘制了 80%置信区间。

![](img/0947efe669b31111d3d9e0e2c9809b11.png)

浅蓝色阴影的宽度表示回归线周围的置信水平。

## **使用自举计算电流强度**

自举是一种使用随机抽样和替换的测试/度量。它给出了精确度的度量(偏差、方差、置信区间、预测误差等)。)来抽样估计。它允许使用随机抽样方法来估计大多数统计量的抽样分布。它也可以用于构建假设检验。

**示例:**

## 蟒蛇 3

```py
# import libraries
import pandas
import numpy
from sklearn.utils import resample
from sklearn.metrics import accuracy_score
from matplotlib import pyplot as plt

# load dataset
x = numpy.array([180,162,158,172,168,150,171,183,165,176])

# configure bootstrap
n_iterations = 1000 # here k=no. of bootstrapped samples
n_size = int(len(x))

# run bootstrap
medians = list()
for i in range(n_iterations):
   s = resample(x, n_samples=n_size);
   m = numpy.median(s);
   medians.append(m)

# plot scores
plt.hist(medians)
plt.show()

# confidence intervals
alpha = 0.95
p = ((1.0-alpha)/2.0) * 100
lower =  numpy.percentile(medians, p)
p = (alpha+((1.0-alpha)/2.0)) * 100
upper =  numpy.percentile(medians, p)

print(f"\n{alpha*100} confidence interval {lower} and {upper}")
```

导入所有必要的库后，创建一个大小为 n=10 的样本 S，并将其存储在变量 x 中。使用一个简单的循环生成 1000 个人工样本(=k)，每个样本大小为 m=10(因为 m <=n). These samples are called the bootstrapped sample. Their medians are computed and stored in a list ‘medians’. Histogram of Medians from 1000 bootstrapped samples is plotted with the help of *matplotlib* 库，并使用样本统计量的公式置信区间计算统计量的总体值的上限和下限，基于样本数据计算指定置信水平。

![](img/cb73c5a6fa2a397f6ff2b3493251b450.png)

95.0 的置信区间在 161.5 和 176.0 之间