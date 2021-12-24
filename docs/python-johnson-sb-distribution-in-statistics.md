# 统计中的 Python–Johnson SB 分布

> 原文:[https://www . geesforgeks . org/python-Johnson-sb-distribution-in-statistics/](https://www.geeksforgeeks.org/python-johnson-sb-distribution-in-statistics/)

**scipy.stats.johnsonsb()** 是一个 johnsonsb 连续随机变量，用标准格式和一些形状参数定义以完成其规范。

**参数:**

> **q :** 上下尾概率
> T3】x:分位数
> **loc :** 【可选】位置参数。默认= 0
> **比例:**【可选】比例参数。默认值= 1
> **大小:**【整数元组，可选】形状或随机变量。
> **时刻:**【可选】由字母['mvsk']组成；m’=均值，‘v’=方差，‘s’= Fisher 偏斜度，‘k’= Fisher 峰度。(默认值= 'mv ')。
> 
> **结果:**约翰逊 SB 连续随机变量

**代码#1:创建约翰逊 SB 连续随机变量**

```py
# importing library

from scipy.stats import johnsonsb  

numargs = johnsonsb.numargs 
a, b = 4.32, 3.18
rv = johnsonsb(a, b) 

print ("RV : \n", rv)  
```

**输出:**

```py
RV : 
 scipy.stats._distn_infrastructure.rv_frozen object at 0x000002A9D50286C8

```

 **代码#2:约翰逊 SB 连续变量和概率分布**

```py
import numpy as np 
quantile = np.arange (0.01, 1, 0.1) 

# Random Variates 
R = johnsonsb.rvs(a, b, scale = 2, size = 10) 
print ("Random Variates : \n", R) 

# PDF 
R = johnsonsb.pdf(a, b, quantile, loc = 0, scale = 1) 
print ("\nProbability Distribution : \n", R)  
```

**输出:**

```py
Random Variates : 
 [0.42212956 0.60876766 0.35494705 0.42892958 0.25316345 0.51872977
 0.2355019  0.44657975 0.54971277 0.36683771]

Probability Distribution : 
 [0\. 0\. 0\. 0\. 0\. 0\. 0\. 0\. 0\. 0.]

```

**代码#3:图形表示。**

```py
import numpy as np 
import matplotlib.pyplot as plt 

distribution = np.linspace(0, np.minimum(rv.dist.b, 3)) 
print("Distribution : \n", distribution) 

plot = plt.plot(distribution, rv.pdf(distribution)) 
```

**输出:**

```py
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

![](img/c569886321449f5a1504dda9dd81f926.png)

**代码#4:变化的位置参数**

```py
import matplotlib.pyplot as plt 
import numpy as np 

x = np.linspace(0, 5, 100) 

# Varying positional arguments 
y1 = johnsonsb .pdf(x, 1, 3) 
y2 = johnsonsb .pdf(x, 1, 4) 
plt.plot(x, y1, "*", x, y2, "r--") 
```

**输出:**

![](img/e4648b3bd1409242b3e84effd47dd339.png)