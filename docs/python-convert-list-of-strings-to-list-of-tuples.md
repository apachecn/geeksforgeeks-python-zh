# Python |将字符串列表转换为元组列表

> 原文:[https://www . geesforgeks . org/python-convert-list-of-string-to-list-tuples/](https://www.geeksforgeeks.org/python-convert-list-of-strings-to-list-of-tuples/)

有时我们处理不同类型的数据类型，我们需要从一种数据类型转换到另一种数据类型，因此转换总是一个有用的工具。从元组到其他格式的相互转换已经在前面讨论过了。本文讨论的是相反的情况。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`map() + split() + tuple()`**

这个任务可以通过这些功能的组合来实现。`map` 函数可用于将逻辑链接到每个字符串，`split` 函数用于将列表的内部内容拆分到不同的元组属性，元组函数执行形成元组的任务。

```py
# Python3 code to demonstrate
# convert list of strings to list of tuples
# Using map() + split() + tuple()

# initializing list
test_list = ['4, 1', '3, 2', '5, 3']

# printing original list
print("The original list : " + str(test_list))

# using map() + split() + tuple()
# convert list of strings to list of tuples
res = [tuple(map(int, sub.split(', '))) for sub in test_list] 

# print result
print("The list after conversion to tuple list : " + str(res))
```

**Output :**

```py
The original list : ['4, 1', '3, 2', '5, 3']
The list after conversion to tuple list : [(4, 1), (3, 2), (5, 3)]

```

**方法 2:使用`map()` + eval**
这是执行这个特殊任务最优雅的方式。其中 map 函数用于将函数逻辑扩展到整个列表，eval 函数在内部执行相互转换和拆分。

```py
# Python3 code to demonstrate
# convert list of strings to list of tuples
# Using map() + eval

# initializing list
test_list = ['4, 1', '3, 2', '5, 3']

# printing original list
print("The original list : " + str(test_list))

# using map() + eval
# convert list of strings to list of tuples
res = list(map(eval, test_list))

# print result
print("The list after conversion to tuple list : " + str(res))
```

**Output :**

```py
The original list : ['4, 1', '3, 2', '5, 3']
The list after conversion to tuple list : [(4, 1), (3, 2), (5, 3)]

```