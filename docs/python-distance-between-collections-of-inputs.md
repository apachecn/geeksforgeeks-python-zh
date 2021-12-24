# Python–输入集合之间的距离

> 原文:[https://www . geeksforgeeks . org/python-输入集合之间的距离/](https://www.geeksforgeeks.org/python-distance-between-collections-of-inputs/)

**scipy.stats.cdist(array，axis=0)** 函数计算两个输入集合的每对之间的距离。

> **参数:**
> **数组:**输入数组或具有计算两个输入集合的每对之间的距离的元素的对象。
> **轴:**要沿其计算的轴。默认情况下，轴= 0
> 
> **返回:**两个输入集合的每对之间的距离。

**代码#1 : 2D 阵**

```py
from scipy.spatial.distance import cdist
a = [[1, 3, 27], [3, 6, 8]]
arr1 = cdist(a, a) 

print("Value of cdist is :", arr1) 
```

**输出:**

```py
Value of cdist is : [[ 0\.         19.33907961]
 [19.33907961  0\.        ]]

```

**代码#2 : 3D 阵列**

```py
from scipy.spatial.distance import cdist

arr1 = [[1, 3, 27],  
        [3, 4, 6],  
        [7, 6, 3],  
        [3, 6, 8]]  

print("Value of cdist is :", cdist(arr1, arr1))  
```

**输出:**

```py
Value of cdist is : [[ 0\.         21.11871208 24.91987159 19.33907961]
 [21.11871208  0\.          5.38516481  2.82842712]
 [24.91987159  5.38516481  0\.          6.40312424]
 [19.33907961  2.82842712  6.40312424  0\.        ]]

```