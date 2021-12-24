# Python |连续元素最大乘积

> 原文:[https://www . geesforgeks . org/python-continuous-element-maximum-product/](https://www.geeksforgeeks.org/python-consecutive-element-maximum-product/)

有时，我们可能会遇到这样的问题，即我们需要从列表中获取 2 个数字的最大乘积，但有一个限制，即这些数字必须连续。这种类型的问题可能在竞争性编程时出现。让我们讨论一下解决这个问题的某些方法。

**方法一:使用`max() + zip()` +列表理解**

这个问题可以用上述三个函数的组合来解决，其中 max 函数可以用来获得最大值，zip 和 list 理解完成了将逻辑扩展到整个列表的任务。

```py
# Python3 code to demonstrate
# Consecutive element maximum product
# using zip() + max() + list comprehension

# initializing string 
test_string = '2312231223124565128998'

# printing original string 
print("The original string : " + str(test_string))

# using zip() + max() + list comprehension
# Consecutive element maximum product
test_string = list(test_string)
res = max(int(a) * int(b) for a, b in zip(test_string, test_string[1:]))

# print result
print("The maximum consecutive product is : " + str(res))
```

**Output :**

```py
The original string : 2312231223124565128998
The maximum consecutive product is : 81

```

**方法 2:使用`max() + map() + operator.mul`**

上述问题也可以使用另一种功能组合来解决。在这种组合中，map 函数执行将逻辑扩展到整个列表的任务，mul 运算符用于执行乘法。

```py
# Python3 code to demonstrate
# Consecutive element maximum product
# using max() + map() + operator.mul
from operator import mul

# initializing string 
test_string = '6543452345456987653234'

# printing original string 
print("The original string : " + str(test_string))

# using max() + map() + operator.mul
# Consecutive element maximum product
res = max(map(mul, map(int, test_string), map(int, test_string[1:])))

# print result
print("The maximum consecutive product is : " + str(res))
```

**Output :**

```py
The original string : 6543452345456987653234
The maximum consecutive product is : 72

```