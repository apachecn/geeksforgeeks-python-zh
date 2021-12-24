# Python |用列表索引值初始化字典

> 原文:[https://www . geesforgeks . org/python-initialization-dictionary-with-list-index-values-2/](https://www.geeksforgeeks.org/python-initializing-dictionary-with-list-index-values-2/)

在使用 Python 时，我们可能需要执行一些任务，其中我们需要分配一个字典，将列表值作为字典值，将索引作为字典键。这类问题在我们需要执行数据类型转换的情况下非常常见。让我们讨论执行这项任务的某些方法。

**方法一:利用字典理解+ `len()`**

该任务可以使用上述功能的组合来执行，其中我们使用字典理解来执行字典的构建，并使用`len`功能来索引有限的内容。

```
# Python3 code to demonstrate working of
# Initializing dictionary with list index-values
# Using dictionary comprehension + len()

# initializing list
test_list = ['Gfg', 'is', 'best']

# printing original list
print("The original list is : " + str(test_list))

# Initializing dictionary with list index-values
# Using dictionary comprehension + len()
res = {x : test_list[x] for x in range(len(test_list))}

# printing result
print("The dictionary indexed as list is :  " + str(res))
```

**Output :**

```
The original list is : ['Gfg', 'is', 'best']
The dictionary indexed as list is :  {0: 'Gfg', 1: 'is', 2: 'best'}

```

**方法 2:使用`dict() + enumerate()`**

这些方法的组合也可用于执行此任务。在这种情况下，我们使用`enumerate` 函数的质量来获取索引，`dict()`用于将列表转换为字典。

```
# Python3 code to demonstrate working of
# Initializing dictionary with list index-values
# Using dict() + enumerate()

# initializing list
test_list = ['Gfg', 'is', 'best']

# printing original list
print("The original list is : " + str(test_list))

# Initializing dictionary with list index-values
# Using dict() + enumerate()
res = dict(enumerate(test_list))

# printing result
print("The dictionary indexed as list is :  " + str(res))
```

**Output :**

```
The original list is : ['Gfg', 'is', 'best']
The dictionary indexed as list is :  {0: 'Gfg', 1: 'is', 2: 'best'}

```