# 如何在 Python 中将一维数组作为列转换成二维数组？

> 原文:[https://www . geeksforgeeks . org/如何将一维数组转换为 python 中的二维数组/](https://www.geeksforgeeks.org/how-to-convert-1-d-arrays-as-columns-into-a-2-d-array-in-python/)

让我们看看一个使用 Python 中的 NumPy 库将一维数组转换为二维数组的程序。所以，为了解决这个问题，我们使用了 numpy 的[**NumPy . column _ stack()**](https://www.geeksforgeeks.org/numpy-column_stack-in-python/)函数。这个函数接受一系列一维数组，并将它们堆叠成列，形成一个二维数组。

> **语法:** numpy.column_stack(元组)
> 
> **参数:**
> 
> tup:[数组序列]包含要堆叠的数组的元组。数组必须具有相同的第一维。
> 
> **返回:**【堆叠二维数组】输入数组的堆叠二维数组。

现在，让我们看一个例子:

**例 1:**

## 蟒蛇 3

```
# import library
import numpy as np

# create a 1d-array
a = np.array(("Geeks", "for",
              "geeks"))

# create a 1d-array
b = np.array(("my", "name",
              "sachin"))

# convert 1d-arrays into
# columns of 2d-array
c = np.column_stack((a, b))

print(c)
```

**输出:**

```
[['Geeks' 'my']
 ['for' 'name']
 ['geeks' 'sachin']]
```

**例 2:**

## 蟒蛇 3

```
# import library
import numpy as np

# create 1d-array
a = np.array((1,2,3,4))

# create 1d-array
b = np.array((5,6,7,8))

# convert 1d-arrays into
# columns of 2d-array
c = np.column_stack((a, b)) 

print(c)
```

**输出:**

```
[[1 5]
[2 6]
[3 7]
[4 8]]
```