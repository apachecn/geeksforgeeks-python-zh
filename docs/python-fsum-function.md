# Python | fsum()函数

> 原文:[https://www.geeksforgeeks.org/python-fsum-function/](https://www.geeksforgeeks.org/python-fsum-function/)

***fsum()*** 是 Python 中的内置函数，用于查找某个范围或可迭代之间的和。要使用这个函数，我们需要导入数学库。

**语法:**

```py
maths.fsum( iterable )

```

**参数:**

```py
iterable : Here we pass some value
which is iterable like arrays, list.
```

**使用:**

```py
fsum() is used to find the sum
of some range, array , list.
```

**返回类型:**

```py
The function return a
floating point number.
```

演示 ***fsum()*** 的代码:

```py
# Python code to demonstrate use  
# of math.fsum() function

# fsum() is found in math library
import math

# range(10)
print(math.fsum(range(10)))

# Integer list
arr = [1, 4, 6]
print(math.fsum(arr))

# Floating point list
arr = [2.5, 2.4, 3.09]
print(math.fsum(arr))
```

输出:

```py
45.0
11.0
7.99

```