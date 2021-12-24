# Python |获取字典中的第一个关键字

> 原文:[https://www . geesforgeks . org/python-获取字典中的第一个键/](https://www.geeksforgeeks.org/python-get-the-first-key-in-dictionary/)

很多时候，在使用 Python 时，我们可能会遇到这样的情况:我们需要获取字典的初始密钥。它可以有许多特定的用途，要么用于检查索引，还有更多这样的用途。让我们讨论执行这项任务的某些方法。

**方法#1:使用`list() + keys()`**

上述方法的组合可用于执行该特定任务。在这种情况下，我们只需将`keys()`提取的整个字典的键转换成一个列表，只需访问第一个键。在使用它时，你必须记住一件事，那就是它的复杂性。它将首先通过迭代每个项目将整个字典转换为列表，然后提取它的第一个元素。使用这种方法，复杂度为 0(n)。

```py
# Python3 code to demonstrate working of
# Getting first key in dictionary
# Using keys() + list()

# initializing dictionary
test_dict = {'Gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using keys() + list()
# Getting first key in dictionary
res = list(test_dict.keys())[0]

# printing initial key
print("The first key of dictionary is : " + str(res))
```

**Output :**

```py
The original dictionary is : {'best': 3, 'Gfg': 1, 'is': 2}
The first key of dictionary is : best

```

**方法 2:使用`next() + iter()`**
这个任务也可以使用这些功能来执行。在这种情况下，我们只需使用`next()`取第一个下一个键，并使用`iter`函数来获得字典项目的可迭代转换。所以如果你只想要第一把钥匙，那么这个方法更有效。它的复杂性是 0(1)。

```py
# Python3 code to demonstrate working of
# Getting first key in dictionary
# Using next() + iter()

# initializing dictionary
test_dict = {'Gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using next() + iter()
# Getting first key in dictionary
res = next(iter(test_dict))

# printing initial key
print("The first key of dictionary is : " + str(res))
```

**Output :**

```py
The original dictionary is : {'best': 3, 'Gfg': 1, 'is': 2}
The first key of dictionary is : best

```