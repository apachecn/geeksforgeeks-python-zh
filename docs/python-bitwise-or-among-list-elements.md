# Python |列表元素之间的位或

> 原文:[https://www . geesforgeks . org/python-按位或列表元素/](https://www.geeksforgeeks.org/python-bitwise-or-among-list-elements/)

有时，在编程时，我们会遇到一个问题，即我们可能需要在列表元素之间执行某些按位运算。这是一个必不可少的工具，因为我们会多次遇到按位运算。让我们讨论执行这项任务的某些方法。

**方法#1:使用`reduce() + lambda + "|"`操作符**
可以组合以上功能来执行此任务。我们可以使用 reduce()来累加 lambda 函数指定的 OR 逻辑的结果。仅适用于 Python2。

```py
# Python code to demonstrate working of
# Bitwise OR among List elements
# Using reduce() + lambda + "|" operator

# initializing list
test_list = [7, 8, 9, 1, 10, 7]

# printing original list
print("The original list is : " + str(test_list))

# Bitwise OR among List elements
# Using reduce() + lambda + "|" operator
res = reduce(lambda x, y: x | y, test_list)

# printing result 
print("The Bitwise OR of list elements are : " + str(res))
```

**Output :**

```py
The original list is : [7, 8, 9, 1, 10, 7]
The Bitwise OR of list elements are : 15

```