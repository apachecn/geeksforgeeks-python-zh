# Python–统计学中的伯努利分布

> 原文:[https://www . geesforgeks . org/python-Bernoulli-distribution-in-statistics/](https://www.geeksforgeeks.org/python-bernoulli-distribution-in-statistics/)

**scipy.stats.bernoulli()** 是一个 bernoulli 离散随机变量。它继承自泛型方法的，作为 **rv_discrete 类**的实例。它用特定于这个特定分布的细节来完成这些方法。

**参数:**

> **x :** 分位数
> **loc :** 【可选】位置参数。默认= 0
> **刻度:**【可选】刻度参数。默认= 1
> **时刻:**【可选】由字母['mvsk']组成；m’=均值，‘v’=方差，‘s’= Fisher 偏斜度，‘k’= Fisher 峰度。(默认值= 'mv ')。
> 
> **结果:**伯努利离散随机变量

**代码#1:创建伯努利离散随机变量**

```
# importing library

from scipy.stats import bernoulli 

numargs = bernoulli .numargs 
a, b = 0.2, 0.8
rv = bernoulli (a, b) 

print ("RV : \n", rv)  
```

**输出:**

```
RV : 
 scipy.stats._distn_infrastructure.rv_frozen object at 0x0000016A4C0FC108

```

**代码#2:伯努利离散变量和概率分布**

```
import numpy as np 
quantile = np.arange (0.01, 1, 0.1) 

# Random Variates 
R = bernoulli .rvs(a, b, size = 10) 
print ("Random Variates : \n", R) 

# PDF 
x = np.linspace(bernoulli.ppf(0.01, a, b),
                bernoulli.ppf(0.99, a, b), 10)
R = bernoulli.ppf(x, 1, 3)
print ("\nProbability Distribution : \n", R) 
```

**输出:**

```
Random Variates : 
 [0 0 0 0 0 0 0 0 0 1]

Probability Distribution : 
 [ 4\.  4\. nan nan nan nan nan nan nan nan]

```

**代码#3:图形表示。**

```
import numpy as np 
import matplotlib.pyplot as plt 

distribution = np.linspace(0, np.minimum(rv.dist.b, 2)) 
print("Distribution : \n", distribution) 

plot = plt.plot(distribution, rv.ppf(distribution)) 
```

**输出:**

```
Distribution : 
 [0\.         0.02040816 0.04081633 0.06122449 0.08163265 0.10204082
 0.12244898 0.14285714 0.16326531 0.18367347 0.20408163 0.2244898
 0.24489796 0.26530612 0.28571429 0.30612245 0.32653061 0.34693878
 0.36734694 0.3877551  0.40816327 0.42857143 0.44897959 0.46938776
 0.48979592 0.51020408 0.53061224 0.55102041 0.57142857 0.59183673
 0.6122449  0.63265306 0.65306122 0.67346939 0.69387755 0.71428571
 0.73469388 0.75510204 0.7755102  0.79591837 0.81632653 0.83673469
 0.85714286 0.87755102 0.89795918 0.91836735 0.93877551 0.95918367
 0.97959184 1\.        ]

```

![](img/af359f706fc5830d1f0545d1ef3e5836.png)

**代码#4:变化的位置参数**

```
import matplotlib.pyplot as plt 
import numpy as np 

x = np.linspace(0, 5, 100) 

# Varying positional arguments 
y1 = bernoulli.ppf(x, a, b) 
y2 = bernoulli.pmf(x, a, b) 
plt.plot(x, y1, "*", x, y2, "r--") 
```

**输出:**

![](img/4e9e9ce391a38653ed53c39d3b9d8b10.png)