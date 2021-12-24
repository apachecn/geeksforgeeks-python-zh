# 如何获取 Python 数组中某个元素的地址？

> 原文:[https://www . geesforgeks . org/如何获取 python 数组中元素的地址/](https://www.geeksforgeeks.org/how-to-get-the-address-for-an-element-in-python-array/)

在本文中，我们将讨论如何获取 Python 数组中特定元素的地址。在 python 中，我们可以使用 numpy 创建数组。Numpy 代表用于创建和处理数组的数字 python。我们必须导入 numpy 模块

> 将 numpy 作为 np 导入

创建数组的语法:

> np.ndarray([element1，element2，…。，元素 n])

## 方法 1:使用数据

我们可以通过数组索引使用**数据**得到地址。

**语法:**

> 数组[索引]。数据

它将返回给定索引处该元素的内存。下面给出了相同的实现。

**示例:**创建 10 个元素的数组并访问某些元素的内存的 Python 代码

## 蟒蛇 3

```
# import numpy module
import numpy as np

# create an array of 10 elements
a = np.array([1, 2, 3, 4, 5, 6, 7, 34, 56, 78])

# get index 4 element address
print("The element present at 4 th  index - element",
      a[4], ":", a[4].data)

# get index 5 element address
print("The element present at 5 th index - element",
      a[5], ":", a[5].data)

# get index 1 element address
print("The element present at 1 st index - element",
      a[1], ":", a[1].data)

# get index 0 element address
print("The element present at 0 th  index - element",
      a[0], ":", a[0].data)
```

**输出:**

> 出现在第 4 个索引处的元素–元素 5 :
> 
> 第 5 个索引处的元素–元素 6 :
> 
> 出现在第一个索引处的元素–元素 2 :
> 
> 出现在第 0 个索引处的元素–元素 1 :

## **方法二:使用 __array_interface__**

我们可以通过使用这个方法获得所有的内存细节，所以显然内存地址也会被返回。

**语法:**

> arr[索引]。__array_interface__

**示例:**获取数组元素地址细节的 Python 代码

## 蟒蛇 3

```
# import numpy module
import numpy as np

# create an array of 10 elements
a = np.array([1, 2, 3, 4, 5, 6, 7, 34, 56, 78])

# get index 4 element address
print("The element present at 4 th  index - element",
      a[4], ":", a[4].__array_interface__)

# get index 5 element address
print("The element present at 5 th index - element",
      a[5], ":", a[5].__array_interface__)

# get index 1 element address
print("The element present at 1 st index - element",
      a[1], ":", a[1].__array_interface__)

# get index 0 element address
print("The element present at 0 th  index - element",
      a[0], ":", a[0].__array_interface__)
```

**输出:**

> 出现在第 4 个索引处的元素–元素 5:{“data”:(94734975551568，False)、“strips”:None、‘descr’:[("、“< i8”)]、“typestr”:“< i8”、“shape”:()、“version”:3、“_ _ ref”:array(5)}
> 
> 出现在第 5 个索引处的元素–元素 6:{“data”:(94734975551568，False)、“strips”:None、‘descr’:[("、“< i8”)]、“typestr”:“< i8”、“shape”:()、“version”:3、“_ _ ref”:array(6)}
> 
> 出现在第一个索引处的元素–元素 2:{“data”:(94734975551568，False)、“steps”:None、‘descr’:[("、“< i8”)]、“typestr”:“< i8”、“shape”:()、“version”:3、“_ _ ref”:array(2)}
> 
> 第 0 个索引处存在的元素–元素 1:{“data”:(94734975551568，False)、“steps”:None、‘descr’:[("、“< i8”)]、“typestr”:“< i8”、“shape”:()、“version”:3、“_ _ ref”:array(1)}