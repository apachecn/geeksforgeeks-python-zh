# Python |将字符串列表转换成多种情况

> 原文:[https://www . geesforgeks . org/python-convert-string-list-to-multi-cases/](https://www.geeksforgeeks.org/python-convert-string-list-into-multiple-cases/)

有时，在使用 Python 字符串时，我们可能会遇到一个问题，即我们有一个字符串列表，我们希望将它们转换为指定的情况。这个问题通常发生在我们收到的字符串大小写错误的情况下。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+内置函数**
在该方法中，我们使用列表理解作为执行该任务的缩短方式，而不是可能跨越某些代码行的循环方法。转换是使用可以执行相互转换任务的通用内置函数进行的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert string list into multiple cases
# Using inbuilt functions + list comprehension

# Initializing list
test_list = ['bLue', 'ReD', 'yeLLoW']

# printing original list
print("The original list is : " + str(test_list))

# Convert string list into multiple cases
# Using inbuilt functions + list comprehension
res = [(ele.upper(), ele.title(), ele.lower()) for ele in test_list]

# printing result
print("The list with multiple cases are : " + str(res))
```

**Output : **

```
The original list is : ['bLue', 'ReD', 'yeLLoW']
The list with multiple cases are : [('BLUE', 'Blue', 'blue'), ('RED', 'Red', 'red'), ('YELLOW', 'Yellow', 'yellow')]
```

**方法 2:使用 map() + lambda +内置函数**
这是执行这个特定任务的另一种方法。在这种情况下，我们只需执行使用 lambda 和迭代扩展转换逻辑的任务，对每个字符串的应用都是由 lambda 函数完成的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert string list into multiple cases
# Using map() + lambda + inbuilt functions

# Initializing list
test_list = ['bLue', 'ReD', 'yeLLoW']

# printing original list
print("The original list is : " + str(test_list))

# Convert string list into multiple cases
# Using map() + lambda + inbuilt functions
res = list(map(lambda ele: (ele.upper(), ele.title(), ele.lower()), test_list))

# printing result
print("The list with multiple cases are : " + str(res))
```

**Output : **

```
The original list is : ['bLue', 'ReD', 'yeLLoW']
The list with multiple cases are : [('BLUE', 'Blue', 'blue'), ('RED', 'Red', 'red'), ('YELLOW', 'Yellow', 'yellow')]
```