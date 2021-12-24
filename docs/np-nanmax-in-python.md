# Python 中的 np.nanmax()

> 原文:[https://www.geeksforgeeks.org/np-nanmax-in-python/](https://www.geeksforgeeks.org/np-nanmax-in-python/)

`**numpy.nanmax()**`函数用于返回一个数组的最大值或沿该数组的任何特定提及的轴，忽略任何 Nan 值。

> **语法:** numpy.nanmax(arr，axis =无，out =无，keepdims =无值)
> 
> **参数:**
> **arr :** 输入数组。
> **轴:**我们想要最大值的轴。否则，将认为 arr 被展平(在所有轴上工作)轴= 0 表示沿列
> 工作，轴= 1 表示沿行工作。
> **出:**不同的数组中我们要放置的结果。数组必须具有与预期输出相同的维度。
> **保持尺寸:**如果设置为真，减少的轴将作为尺寸为 1 的尺寸留在结果中。使用此选项，结果将根据原始 a 正确广播。
> 
> **返回:**最大数组值(如果轴为无，则为标量值)或沿指定轴具有最大值的数组。

**代码#1:工作**

```
# Python Program illustrating 
# numpy.nanmax() method 

import numpy as np

# 1D array 
arr = [1, 2, 7, 0, np.nan]
print("arr : ", arr) 
print("max of arr : ", np.amax(arr))

# nanmax ignores NaN values. 
print("nanmax of arr : ", np.nanmax(arr))

```

**输出:**

```
arr :  [1, 2, 7, 0, nan]
max of arr :  nan
nanmax of arr :  7.0

```

**代码#2 :**

```
import numpy as np

# 2D array 
arr = [[np.nan, 17, 12, 33, 44],  
       [15, 6, 27, 8, 19]] 
print("\narr : \n", arr) 

# maximum of the flattened array 
print("\nmax of arr, axis = None : ", np.nanmax(arr)) 

# maximum along the first axis 
# axis 0 means vertical 
print("max of arr, axis = 0 : ", np.nanmax(arr, axis = 0)) 

# maximum along the second axis 
# axis 1 means horizontal 
print("max of arr, axis = 1 : ", np.nanmax(arr, axis = 1)) 
```

**输出:**

```
arr : 
 [[nan, 17, 12, 33, 44], [15, 6, 27, 8, 19]]

max of arr, axis = None :  44.0
max of arr, axis = 0 :  [15\. 17\. 27\. 33\. 44.]
max of arr, axis = 1 :  [44\. 27.]

```

**代码#3 :**

```
import numpy as np

arr1 = np.arange(5) 
print("Initial arr1 : ", arr1)

# using out parameter
np.nanmax(arr, axis = 0, out = arr1)

print("Changed arr1(having results) : ", arr1)  
```

**输出:**

```
Initial arr1 :  [0 1 2 3 4]
Changed arr1(having results) :  [15 17 27 33 44]

```