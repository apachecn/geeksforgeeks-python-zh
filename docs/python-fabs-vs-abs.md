# Python | fabs() vs abs()

> 原文:[https://www.geeksforgeeks.org/python-fabs-vs-abs/](https://www.geeksforgeeks.org/python-fabs-vs-abs/)

[abs()](https://www.geeksforgeeks.org/abs-in-python/) 和 fabs()函数都是用来求一个数的绝对值，即去掉一个数的负号。

**ABS()的语法:**

```py
abs(number)
```

**fabs()的语法:**

```py
math.fabs(number)
```

两者都将返回一个数字的绝对值。

不同之处在于，即使参数是整数，math.fabs(number)也将始终返回一个浮点数，而 abs()将根据参数返回一个浮点数或整数。

如果参数是复数，abs()将返回幅度部分，而 fabs()将返回一个错误。
要使用 fabs()函数，我们需要导入库“math”，而 abs()函数附带 Python 的标准库。

## 蟒蛇 3

```py
# Python code to demonstrate working
# of fabs() and abs()
import math

#################################
# When the argument is an integer#
#################################
number = -10

# abs() will return an integer as
# the argument is an integer
print(abs(number))

# fabs() will return a floating point number
print(math.fabs(number))

###########################################
# When the input is a floating point number#
###########################################
number = -12.08

# abs() will return an floating point number
# as the argument is a floating point number
print(abs(number))

# fabs() will return a floating point number
print(math.fabs(number))

####################################
# When the input is a complex number#
####################################
number = complex(3, 4)

# abs() will return the magnitude
print(abs(number))

# fabs() will return an error
# print(math.fabs(number))
```

**输出:**

```py
10
10.0
12.08
12.08
5.0
```