# Python–两个一维数组之间的布雷-柯蒂斯距离

> 原文:[https://www . geesforgeks . org/python-bray-Curtis-distance-two-1-d-arrays/](https://www.geeksforgeeks.org/python-bray-curtis-distance-between-two-1-d-arrays/)

**scipy.stats.braycurtis(数组，轴=0)** 函数计算两个一维数组之间的 Bray-Curtis 距离。

> **参数:**
> **数组:**输入数组或具有计算两个输入集合的每对之间的距离的元素的对象。
> **轴:**要沿其计算的轴。默认情况下，轴= 0
> 
> **返回:**两个输入集合的每对之间的距离。

**代码#1 : 1D 阵**

```py
from scipy.spatial.distance import braycurtis

a = [3, 1]

b = [2, 1]
arr1 = braycurtis(a, b) 

print("Value of braycurtis is :", arr1) 
```

**输出:**

```py
Value of braycurtis is : 0.14285714285714285

```

**代码#2 : 2D 阵**

```py
from scipy.spatial.distance import braycurtis

arr1 = [1, 3, 27]

arr2 = [3, 6, 8] 

print("Value of braycurtis is :", braycurtis(arr1, arr2))  

```

**输出:**

```py
Value of braycurtis is : 0.5

```