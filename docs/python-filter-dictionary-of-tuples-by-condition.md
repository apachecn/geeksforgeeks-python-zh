# Python |按条件过滤元组字典

> 原文:[https://www . geeksforgeeks . org/python-filter-dictionary-of-tuples-by-condition/](https://www.geeksforgeeks.org/python-filter-dictionary-of-tuples-by-condition/)

有时，我们可能会遇到一个非常具体的问题，即我们被赋予一个元组对作为字典中的值，我们需要根据这些元组对过滤字典项。这个特殊的问题作为竞争程序设计中许多几何算法的用例。让我们讨论执行这项任务的某些方法。

**方法一:使用`items()` +词典理解**
这些功能组合在一起就可以完成这个任务。我们可以使用 `items()`访问所有值，条件可以通过字典理解来施加。

```py
# Python3 code to demonstrate working of
# Filter dictionary of tuples by condition
# Using items() + dictionary comprehension

# initializing dictionary
test_dict = {'a' : (6, 3), 'b' : (4, 8), 'c' : (8, 4)}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Filter dictionary of tuples by condition
# Using items() + dictionary comprehension
res = {key: val for key, val in test_dict.items() if val[0] >= 6 and val[1] <= 4}

# printing result
print("The filtered dictionary is : " +  str(res))
```

**Output :**

```py
The original dictionary is : {'b': (4, 8), 'a': (6, 3), 'c': (8, 4)}
The filtered dictionary is : {'a': (6, 3), 'c': (8, 4)}

```