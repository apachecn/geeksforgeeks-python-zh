# Python–统计中的 Levy _ 稳定分布

> 原文:[https://www . geesforgeks . org/python-levy _ stable-distribution-in-statistics/](https://www.geeksforgeeks.org/python-levy_stable-distribution-in-statistics/)

**scipy . stats . levy _ stable()**是 Levy 稳定的连续随机变量。它继承自泛型方法的，作为 **rv_continuous 类**的实例。它用特定于这个特定分布的细节来完成这些方法。

**参数:**

> **q :** 上下尾概率
> T3】x:分位数
> **loc :** 【可选】位置参数。默认= 0
> **比例:**【可选】比例参数。默认值= 1
> **大小:**【整数元组，可选】形状或随机变量。
> **时刻:**【可选】由字母['mvsk']组成；m’=均值，‘v’=方差，‘s’= Fisher 偏斜度，‘k’= Fisher 峰度。(默认值= 'mv ')。
> 
> **结果:**利维稳定连续随机变量

**代码#1:创建征税稳定的征税连续随机变量**

```py
# importing library

from scipy.stats import levy_stable  

numargs = levy_stable.numargs 
a, b = 4.32, 3.18
rv = levy_stable(a, b) 

print ("RV : \n", rv)  
```

**输出:**

```py
RV : 
 scipy.stats._distn_infrastructure.rv_frozen object at 0x000002A9D6803648

```

 **代码#2:利维稳定连续变量和概率分布**

```py
import numpy as np 
quantile = np.arange (0.03, 2, 0.21) 

# Random Variates 
R = levy_stable.rvs(1.8, -0.5, size = 10) 
print ("Random Variates : \n", R) 

# PDF 
R = levy_stable.pdf(a, b, quantile) 
print ("\nProbability Distribution : \n", R) 
```

**输出:**

```py
Random Variates : 
 [ 1.20654126 -0.56381774 -1.31527459 -0.90027222  0.52535969  0.03076316
 -4.69310302  0.61194358  1.31207992 -0.84552083]

Probability Distribution : 
 [nan nan nan nan nan nan nan nan nan nan]

```

**代码#3:图形表示。**

```py
import numpy as np 
import matplotlib.pyplot as plt 

distribution = np.linspace(levy_stable.ppf(0.01, 1.8, -0.5), 
                           levy_stable.ppf(0.99, 1.8, -0.5), 100) 
print("Distribution : \n", distribution)  
```

**输出:**

```py
Distribution : 
 [-4.92358285 -4.8368521  -4.75012136 -4.66339061 -4.57665986 -4.48992912
 -4.40319837 -4.31646762 -4.22973687 -4.14300613 -4.05627538 -3.96954463
 -3.88281389 -3.79608314 -3.70935239 -3.62262164 -3.5358909  -3.44916015
 -3.3624294  -3.27569866 -3.18896791 -3.10223716 -3.01550641 -2.92877567
 -2.84204492 -2.75531417 -2.66858343 -2.58185268 -2.49512193 -2.40839118
 -2.32166044 -2.23492969 -2.14819894 -2.06146819 -1.97473745 -1.8880067
 -1.80127595 -1.71454521 -1.62781446 -1.54108371 -1.45435296 -1.36762222
 -1.28089147 -1.19416072 -1.10742998 -1.02069923 -0.93396848 -0.84723773
 -0.76050699 -0.67377624 -0.58704549 -0.50031475 -0.413584   -0.32685325
 -0.2401225  -0.15339176 -0.06666101  0.02006974  0.10680048  0.19353123
  0.28026198  0.36699273  0.45372347  0.54045422  0.62718497  0.71391571
  0.80064646  0.88737721  0.97410796  1.0608387   1.14756945  1.2343002
  1.32103094  1.40776169  1.49449244  1.58122319  1.66795393  1.75468468
  1.84141543  1.92814618  2.01487692  2.10160767  2.18833842  2.27506916
  2.36179991  2.44853066  2.53526141  2.62199215  2.7087229   2.79545365
  2.88218439  2.96891514  3.05564589  3.14237664  3.22910738  3.31583813
  3.40256888  3.48929962  3.57603037  3.66276112]
```