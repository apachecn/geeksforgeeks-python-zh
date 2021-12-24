# Python–统计中向左倾斜的征税分布

> 原文:[https://www . geesforgeks . org/python-左倾-征收-统计中的分布/](https://www.geeksforgeeks.org/python-left-skewed-levy-distribution-in-statistics/)

**scipy.stats.levy_l()** 是左偏 levy 连续随机变量。它继承自泛型方法的，作为 **rv_continuous 类**的实例。它用特定于这个特定分布的细节来完成这些方法。

**参数:**

> **q :** 上下尾概率
> T3】x:分位数
> **loc :** 【可选】位置参数。默认= 0
> **比例:**【可选】比例参数。默认值= 1
> **大小:**【整数元组，可选】形状或随机变量。
> **时刻:**【可选】由字母['mvsk']组成；m’=均值，‘v’=方差，‘s’= Fisher 偏斜度，‘k’= Fisher 峰度。(默认值= 'mv ')。
> 
> **结果:**左偏 Levy 连续随机变量

**代码#1:创建左偏斜 Levy 连续随机变量**

```py
# importing library

from scipy.stats import levy_l  

numargs = levy_l.numargs 
a, b = 4.32, 3.18
rv = levy_l(a, b) 

print ("RV : \n", rv)  
```

**输出:**

```py
RV : 
 scipy.stats._distn_infrastructure.rv_frozen object at 0x000002A9D6707508

```

 **代码#2:左偏李维连续变量和概率分布**

```py
import numpy as np 
quantile = np.arange (0.03, 2, 0.21) 

# Random Variates 
R = levy_l.rvs(a, b) 
print ("Random Variates : \n", R) 

# PDF 
R = levy_l.pdf(a, b, quantile) 
print ("\nProbability Distribution : \n", R) 
```

**输出:**

```py
Random Variates : 
 1.1073459342251062

Probability Distribution : 
 [0\. 0\. 0\. 0\. 0\. 0\. 0\. 0\. 0\. 0.]

```

**代码#3:图形表示。**

```py
import numpy as np 
import matplotlib.pyplot as plt 

distribution = np.linspace(0, np.maximum(rv.dist.b, 4)) 
print("Distribution : \n", distribution) 

plot = plt.plot(distribution, rv.pdf(distribution))  
```

**输出:**

```py
Distribution : 
 [0\.         0.08163265 0.16326531 0.24489796 0.32653061 0.40816327
 0.48979592 0.57142857 0.65306122 0.73469388 0.81632653 0.89795918
 0.97959184 1.06122449 1.14285714 1.2244898  1.30612245 1.3877551
 1.46938776 1.55102041 1.63265306 1.71428571 1.79591837 1.87755102
 1.95918367 2.04081633 2.12244898 2.20408163 2.28571429 2.36734694
 2.44897959 2.53061224 2.6122449  2.69387755 2.7755102  2.85714286
 2.93877551 3.02040816 3.10204082 3.18367347 3.26530612 3.34693878
 3.42857143 3.51020408 3.59183673 3.67346939 3.75510204 3.83673469
 3.91836735 4\.        ]

```

![](img/cc7ef139c9fbe62159122a57154eb077.png)
**代码#4:不同的位置参数**

```py
import matplotlib.pyplot as plt 
import numpy as np 

x = np.linspace(0, 5, 100) 

# Varying positional arguments 
y1 = levy_l .pdf(x, 1, 3) 
y2 = levy_l .pdf(x, 1, 4) 
plt.plot(x, y1, "*", x, y2, "r--") 
```

**输出:**
![](img/ac63fd20c4d437e858103a39d20866aa.png)