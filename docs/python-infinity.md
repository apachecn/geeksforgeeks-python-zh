# Python infinity

> 原文:[https://www.geeksforgeeks.org/python-infinity/](https://www.geeksforgeeks.org/python-infinity/)

具有讽刺意味的是，无穷大被定义为一个不确定的数字，它可以是正值，也可以是负值。对一个无穷大的值执行的所有算术运算总会得到一个无穷大的数，比如说它是和、减、乘或任何其他运算。
在计算机科学领域，infinity 通常用于衡量性能和优化在大规模应用程序上执行计算的算法。

**用 python 把无穷大表示为整数**
把无穷大表示为整数的概念违反了无穷大本身的定义。截至 2020 年，迄今为止，在任何编程语言中都没有这样的方法将无穷大表示为整数。但是在 python 中，由于它是一种动态语言，浮点值可以用来表示无限整数。可以使用 **float('inf')** 作为整数来表示它为无穷大。下面是 Python 中表示无穷大的方法列表。

**1。使用浮点(' inf ')和浮点('-inf'):**

由于无穷大可以是正的，也可以是负的，所以它们可以分别表示为浮点数(' inf ')和浮点数('-inf ')。下面的代码显示了上述内容的实现:

## 蟒蛇 3

```
# Defining a positive infinite integer
positive_infinity = float('inf')
print('Positive Infinity: ', positive_infinity)

# Defining a negative infinite integer
negative_infinity = float('-inf')
print('Negative Infinity: ', negative_infinity)
```

**输出:**

```
Positive Infinity:  inf
Negative Infinity:  -inf
```

**2。使用 Python 的数学模块:**

Python 的数学模块也可以用来表示无限整数。下面的代码显示了它是如何实现的:

## 蟒蛇 3

```
import math

# Defining a positive infinite integer
positive_infinity = math.inf
print('Positive Infinity: ', positive_infinity)

# Defining a negative infinite integer
negative_infinity = -math.inf
print('Negative Infinity: ', negative_infinity)
```

**输出:**

```
Positive Infinity:  inf
Negative Infinity:  -inf
```

**3。使用 Python 的十进制模块:**

Python 的十进制模块也可以用来表示无限浮点值。
正值用做**小数(【无穷大】)**，负值用做**小数(【无穷大】)**。

下面的代码显示了它的实现:

## 蟒蛇 3

```
from decimal import Decimal

# Defining a positive infinite integer
positive_infinity = Decimal('Infinity')
print('Positive Infinity: ', positive_infinity)

# Defining a negative infinite integer
negative_infinity = Decimal('-Infinity')
print('Negative Infinity: ', negative_infinity)
```

**输出:**

```
Positive Infinity:  Infinity
Negative Infinity:  -Infinity
```

**4。使用 Python 的 Numpy 库:**

Python 的 Numpy 模块也可以用来表示无穷大的值。正值用 **np.inf** ，负值用 **-np.inf** 。使用 Numpy 库来表示一个无穷大的值，如下代码所示:

## 蟒蛇 3

```
import numpy as np

# Defining a positive infinite integer
positive_infinity = np.inf
print('Positive Infinity: ', positive_infinity)

# Defining a negative infinite integer
negative_infinity = -np.inf
print('Negative Infinity: ', negative_infinity)
```

**输出:**

```
Positive Infinity:  inf
Negative Infinity:  -inf
```

**在 Python 中检查一个数是否是无限的**
要检查一个给定的数是否是无限的，可以使用数学库的 **isinf()** 方法，该方法返回一个布尔值。下面的代码显示了 isinf()方法的使用:

## 蟒蛇 3

```
import numpy as np
import math

# Defining a positive infinite integer
a = np.inf

# Defining a negative infinite integer
b = -np.inf

# Define a finite integer
c = 300

# check if a in infinite
print(math.isinf(a))

# check if b in infinite
print(math.isinf(b))

# check if c in infinite
print(math.isinf(c))
```

**输出:**

```
True
True
False
```

**python 中无限值与有限值的比较**
将无限值与有限值进行比较的概念就这么简单。因为正无穷大总是大于每个自然数，负无穷大总是小于负数。为了更好地理解，请看下面的代码:

## 蟒蛇 3

```
import numpy as np

# Defining a positive infinite integer
a = np.inf

# Defining a negative infinite integer
b = -np.inf

# Define a finite + ve integer
c = 300

# Define a finite -ve integer
d = -300

# helper function to make comparisons
def compare(x, y):
    if x>y:
        print("True")
    else:
        print("False")

compare(a, b)
compare(a, c)
compare(a, d)
compare(b, c)
compare(b, d)
```

**输出:**

```
True
True
True
False
False
```