# Python |用公共值初始化字典

> 原文:[https://www . geesforgeks . org/python-initialize-dictionary-with-common-value/](https://www.geeksforgeeks.org/python-initialize-dictionary-with-common-value/)

在使用 Python 时，有时我们可能会遇到一个问题，即我们需要将静态列表初始化为一个具有常数值的字典。让我们讨论执行这项任务的某些方法。

**方法一:使用`dict()` +列表理解**

上述功能的组合可用于执行该特定任务。在这种情况下，我们只需将从列表中提取的元素转换为键，并使用`dict().`完成的列表理解和转换来分配公共值

```
# Python3 code to demonstrate working of
# Initialize dictionary with common value
# Using list comprehension + dict()

# Initialize list
test_list = ['gfg', 'is', 'best']

# printing original list
print("The original list is : " + str(test_list))

# Initialize dictionary with common value
# Using list comprehension + dict()
res = dict((sub, 4) for sub in test_list)

# printing result
print("The constructed dictionary with common value : " + str(res))
```

**Output :**

```
The original list is : ['gfg', 'is', 'best']
The constructed dictionary with common value : {'is': 4, 'gfg': 4, 'best': 4}

```

**方法 2:使用`fromkeys()`**

fromkeys()的内置函数也可以用来执行这个特定的任务，这个任务本身就是为了执行这个特定的任务而做的，并且是执行这个任务的一种更皮通的方式。

```
# Python3 code to demonstrate working of
# Initialize dictionary with common value
# Using fromkeys()

# Initialize list
test_list = ['gfg', 'is', 'best']

# printing original list
print("The original list is : " + str(test_list))

# Initialize dictionary with common value
# Using fromkeys()
res = dict.fromkeys(test_list, 4)

# printing result
print("The constructed dictionary with common value : " + str(res))
```

**Output :**

```
The original list is : ['gfg', 'is', 'best']
The constructed dictionary with common value : {'is': 4, 'gfg': 4, 'best': 4}

```