# Python |获取元组元素数据类型

> 原文:[https://www . geesforgeks . org/python-get-tuple-element-data-types/](https://www.geeksforgeeks.org/python-get-tuple-element-data-types/)

元组可以是各种数据类型的集合，与更简单的数据类型不同，获取元组的每个元素的类型的传统方法是不可能的。为此，我们需要有不同的方法来完成这项任务。让我们讨论执行这项任务的某些方法。

**方法一:使用`map() + type()`**
使用这个功能是执行这个任务最常规也是最好的方式。在这种情况下，我们只允许`map()`将使用`type()`查找数据类型的逻辑扩展到元组的每个元素。

```py
# Python3 code to demonstrate working of
# Get tuple element data types
# Using map() + type()

# Initializing tuple
test_tup = ('gfg', 1, ['is', 'best'])

# printing original tuple
print("The original tuple is : " + str(test_tup))

# Get tuple element data types
# Using map() + type()
res = list(map(type, test_tup))

# printing result
print("The data types of tuple in order are : " + str(res))
```

**Output :**

```py
The original tuple is : ('gfg', 1, ['is', 'best'])
The data types of tuple in order are : [<class 'str'>, <class 'int'>, <class 'list'>]

```