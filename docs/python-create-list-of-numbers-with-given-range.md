# Python |创建给定范围的数字列表

> 原文:[https://www . geeksforgeeks . org/python-创建给定范围的数字列表/](https://www.geeksforgeeks.org/python-create-list-of-numbers-with-given-range/)

给定两个数字 *r1* 和 *r2* (定义了范围)，编写一个 Python 程序，用给定的范围(含)创建一个列表。

**示例:**

```
Input : r1 = -1, r2 = 1
Output : [-1, 0, 1]

Input : r1 = 5, r2 = 9
Output : [5, 6, 7, 8, 9]

```

让我们讨论一些方法来完成这项任务。

**方法#1 :** 简单方法

在给定范围内创建列表的简单方法是首先创建一个空列表，并在 for 循环的每次迭代中追加每个整数的后继值。

```
# Python3 Program to Create list 
# with integers within given range 

def createList(r1, r2):

    # Testing if range r1 and r2 
    # are equal
    if (r1 == r2):
        return r1

    else:

        # Create empty list
        res = []

        # loop to append successors to 
        # list until r2 is reached.
        while(r1 < r2+1 ):

            res.append(r1)
            r1 += 1
        return res

# Driver Code
r1, r2 = -1, 1
print(createList(r1, r2))
```

**Output:**

```
[-1, 0, 1]

```

**方法 2 :** 列表理解

我们也可以使用列表理解来达到这个目的。只需在从 *r1* 到 *r2* 的 for 循环中迭代“项目”，并将所有“项目”作为列表返回。这将是一个简单的一行代码。

```
# Python3 Program to Create list 
# with integers within given range 

def createList(r1, r2):
    return [item for item in range(r1, r2+1)]

# Driver Code
r1, r2 = -1, 1
print(createList(r1, r2))
```

**Output:**

```
[-1, 0, 1]

```

**使用 Python 逼近# 3:**`range()`

Python 附带了一个直接函数`range()`，它创建了一个从开始到停止值的数字序列，并打印序列中的每个项目。我们将`range()`与 *r1* 和 *r2* 一起使用，然后将序列转换为列表。

```
# Python3 Program to Create list 
# with integers within given range 

def createList(r1, r2):
    return list(range(r1, r2+1))

# Driver Code
r1, r2 = -1, 1
print(createList(r1, r2))
```

**Output:**

```
[-1, 0, 1]

```

**使用`numpy.arange()`接近#4 :**

Python numpy.arange()返回一个列表，其中包含按照间隔均匀分布的元素。这里，我们根据需要将间隔设置为 1，以获得所需的输出。

```
# Python3 Program to Create list 
# with integers within given range 
import numpy as np
def createList(r1, r2):
    return np.arange(r1, r2+1, 1)

# Driver Code
r1, r2 = -1, 1
print(createList(r1, r2))
```

**Output:**

```
[-1  0  1]

```