# Python |检查元组中订单特定的数据类型

> 原文:[https://www . geesforgeks . org/python-check-order-specific-data-type-in-tuple/](https://www.geeksforgeeks.org/python-check-order-specific-data-type-in-tuple/)

有时，在处理记录时，我们可能会遇到一个问题，即我们需要测试在填写表单等时插入的数据类型的正确排序。在后端。这些测试通常在 web 开发时在前端处理，但也建议在后端测试。为此，我们有时需要根据记录的排序来检查记录的数据类型。让我们讨论执行这项任务的某些方法。

**方法#1:使用链式`if`和`isinstance()`**
该任务可以使用上述功能的组合来执行。在这种情况下，我们只需要使用 `isintance()`测试数据类型，并检查我们使用的链式 if 语句的每个元组元素。

```
# Python3 code to demonstrate working of
# Check order specific data type in tuple
# Using chained if and isinstance()

# Initializing tuple
test_tup = ('gfg', ['is', 'best'], 1)

# printing original tuple
print("The original tuple is : " + str(test_tup))

# Check order specific data type in tuple
# Using chained if and isinstance()
res = isinstance(test_tup, tuple)\
      and isinstance(test_tup[0], str)\
      and isinstance(test_tup[1], list)\
      and isinstance(test_tup[2], int)

# printing result
print("Does all the instances match required data types in order ? : " + str(res))
```

**Output :**

```
The original tuple is : ('gfg', ['is', 'best'], 1)
Does all the instances match required data types in order ? : True

```