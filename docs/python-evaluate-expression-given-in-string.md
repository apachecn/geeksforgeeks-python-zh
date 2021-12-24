# Python–计算字符串中给出的表达式

> 原文:[https://www . geesforgeks . org/python-evaluate-expression-给定字符串/](https://www.geeksforgeeks.org/python-evaluate-expression-given-in-string/)

有时，在使用 Python Strings 时，我们可以用字符串格式进行某些计算，并且我们需要将其结果公式化。这可能发生在与数学和数据相关的领域。让我们讨论一下执行这项任务的某些方法。

**方法#1:使用 regex + map() + sum()**
以上函数的组合可以用来解决这个问题。在本文中，我们使用 sum()执行计算任务，使用 map()执行运算符和运算的映射。如果字符串只有+或-，则可以使用此方法。方法#2 也可以用于其他操作。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Expression evaluation in String
# Using regex + map() + sum()
import re

# initializing string
test_str = "45 + 98-10"

# printing original string
print("The original string is : " + test_str)

# Expression evaluation in String
# Using regex + map() + sum()
res = sum(map(int, re.findall(r'[+-]?\d+', test_str)))

# printing result
print("The evaluated result is : " + str(res))
```

**Output : **

```py
The original string is : 45+98-10
The evaluated result is : 133
```

**方法 2:使用 eval()**
这是可以执行此任务的方式之一。在本文中，我们使用 eval()在内部执行计算。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Expression evaluation in String
# Using eval()

# initializing string
test_str = "45 + 98-10"

# printing original string
print("The original string is : " + test_str)

# Expression evaluation in String
# Using eval()
res = eval(test_str)

# printing result
print("The evaluated result is : " + str(res))
```

**Output : **

```py
The original string is : 45+98-10
The evaluated result is : 133
```