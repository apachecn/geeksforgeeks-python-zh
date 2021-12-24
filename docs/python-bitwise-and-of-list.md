# Python–列表的逐位“与”

> 原文:[https://www.geeksforgeeks.org/python-bitwise-and-of-list/](https://www.geeksforgeeks.org/python-bitwise-and-of-list/)

有时，在编程时，我们会遇到一个问题，即我们可能需要在列表元素之间执行某些按位运算。这是一个必不可少的工具，因为我们会多次遇到按位运算。让我们讨论执行这项任务的某些方法。
**方法#1:使用 reduce()+lambda+“&”运算符**
以上功能可以组合执行此任务。我们可以使用 reduce()来累加 lambda 函数指定的 AND 逻辑的结果。仅适用于 Python2。

## 蟒蛇 3

```
# Python code to demonstrate working of
# Bitwise AND of List
# Using reduce() + lambda + "&" operator

# initializing list
test_list = [4, 6, 2, 3, 8, 9]

# printing original list
print("The original list is : " + str(test_list))

# Bitwise AND of List
# Using reduce() + lambda + "&" operator
res = reduce(lambda x, y: x & y, test_list)

# printing result
print("The Bitwise AND of list elements are : " + str(res))
```

**Output : **

```
The original list is : [4, 6, 2, 3, 8, 9]
The Bitwise AND of list elements are : 0

```

**方法 2:使用 reduce()+operator . and**
这个任务也可以使用这个方法来执行。在这种情况下，由上述方法中的 lambda 函数执行的任务是使用用于累积 and 运算的 AND 函数来执行的。仅适用于 Python2。

## 蟒蛇 3

```
# Python code to demonstrate working of
# Bitwise AND of List
# Using functools.reduce() + operator.iand
from operator import iand
from functools import reduce
# initializing list
test_list = [4, 6, 2, 3, 8, 9]

# printing original list
print("The original list is : " + str(test_list))

# Bitwise AND of List
# Using functools.reduce() + operator.iand
res = reduce(iand, test_list)

# printing result
print("The Bitwise AND of list elements are : " + str(res))
```

**Output : **

```
The original list is : [4, 6, 2, 3, 8, 9]
The Bitwise AND of list elements are : 0

```