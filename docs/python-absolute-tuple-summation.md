# Python–绝对元组求和

> 原文:[https://www . geesforgeks . org/python-absolute-tuple-summary/](https://www.geeksforgeeks.org/python-absolute-tuple-summation/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要执行中间元组元素绝对值的求和。这种问题可以应用于许多领域，例如 web 开发。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(-7，-8)、(-5，-6)]
> **输出**:【15，11】
> 
> **输入** : test_list = [(-1，-2，-4)]
> **输出**:【7】

**方法#1:使用`sum() + list comprehension + abs()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 sum()，abs()为绝对值执行计算和的任务，并使用列表理解来遍历列表和每个元组内部，使用生成器表达式进行迭代。

```py
# Python3 code to demonstrate working of 
# Absolute Tuple Summation
# Using sum() + list comprehension + abs()

# initializing list
test_list = [(7, -8), (-5, -6), (-7, 2), (6, 8)]

# printing original list
print("The original list is : " + str(test_list))

# Absolute Tuple Summation
# Using sum() + list comprehension + abs()
res = [sum([abs(ele) for ele in sub]) for sub in test_list]

# printing result 
print("The absolute sum list: " + str(res)) 
```

**Output :**

```py
The original list is : [(7, -8), (-5, -6), (-7, 2), (6, 8)]
The absolute sum list: [15, 11, 9, 14]

```

**方法 2:使用列表理解+ `sum() + map()`**
上述功能的组合为解决这个问题提供了一个替代方案。在这种情况下，我们使用 map()而不是生成器表达式来执行计算整个元组元素之和的任务。

```py
# Python3 code to demonstrate working of 
# Absolute Tuple Summation
# Using list comprehension + sum() + map()

# initializing list
test_list = [(7, -8), (-5, -6), (-7, 2), (6, 8)]

# printing original list
print("The original list is : " + str(test_list))

# Absolute Tuple Summation
# Using list comprehension + sum() + map()
res = [sum(map(abs, ele)) for ele in test_list]

# printing result 
print("The absolute sum list: " + str(res)) 
```

**Output :**

```py
The original list is : [(7, -8), (-5, -6), (-7, 2), (6, 8)]
The absolute sum list: [15, 11, 9, 14]

```