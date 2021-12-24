# 检查 Python 中的值是无穷大还是 NaN

> 原文:[https://www . geeksforgeeks . org/check-value-in-infinity-or-nan-in-python/](https://www.geeksforgeeks.org/check-if-the-value-is-infinity-or-nan-in-python/)

在本文中，我们将检查给定值是 NaN 还是 Infinity。这可以使用数学模块来完成。让我们看看如何详细检查每个值。

## **检查数值是否为 NaN**

NaN 代表“**”而不是数字**”，它是一种数字数据类型，用于表示数学上未定义或无法表示的值。有很多这样的例子-

1.  0/0 未定义，NaN 用于表示它。
2.  Sqrt(-ve number)不能存储为实数，因此使用 NaN 表示它。
3.  Log(-ve number)不能存储为实数，因此使用 NaN 表示它。
4.  一个数< -1 or number > 1 的逆 sin 或逆 cos 也是 NaN。
5.  0 * inf 也会导致 NaN。

因为 NaN 本身就是类型，所以它被用来分配尚未计算值的变量。

**方法 1** :要检查 nan，我们可以使用 [**math.isnan()**](https://www.geeksforgeeks.org/python-math-library-isnan-method/) **函数**，因为 NaN 不能使用==运算符进行测试。

## 蟒蛇 3

```py
import math

x = math.nan
print(f"x contains {x}")

# checks if variable is equal to NaN
if(math.isnan(x)):
    print("x == nan")
else:
    print("x != nan")
```

**Output**

```py
x contains nan
x == nan
```

**方法 2:** NaN 不等于 NaN，因此我们可以利用这个属性来检查 NaN。下面的代码演示了它。

## 蟒蛇 3

```py
import math

def isNan(number):

    # This function compares number to itself.
    # NaN != NaN and therefore it will return
    # true if the number is Nan
    return number != number

# Driver Code 
x = math.nan
print(isNan(x))
```

**Output**

```py
True
```

## **检查数值是否为无穷大**

**方法 1:** 要在 python 中检查无穷大，使用的函数是 **math.isinf()** ，它只检查无穷大。为了区分正无穷大和负无穷大，我们可以添加更多的逻辑来检查数字是大于 0 还是小于 0。代码显示了这一点。

## 蟒蛇 3

```py
import math

# Function checks if negative or
# positive infinite.
def check(x):

    if(math.isinf(x) and x > 0):
        print("x is Positive inf")

    elif(math.isinf(x) and x < 0):
        print("x is negative inf")

    else:
        print("x is not inf")

# Creating inf using math module.
number = math.inf
check(number)

number = -math.inf
check(number)
```

**Output**

```py
x is Positive inf
x is negative inf
```

**方法二:** Numpy 还公开了两个 API 来检查正负无穷大。分别是[**NP . isneginf()**](https://www.geeksforgeeks.org/numpy-isneginf-python/)**和**[**NP . isposinf()**](https://www.geeksforgeeks.org/numpy-isposinf-python/)**。******

## ****蟒蛇 3****

```py
**# pip install numpy
import numpy as np

print(np.isneginf([np.inf, 0, -np.inf]))
print(np.isposinf([np.inf, 0, -np.inf]))**
```

******输出******

```py
**[False False  True]
[ True False False]**
```