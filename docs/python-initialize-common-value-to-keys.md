# Python |将公共值初始化为键

> 原文:[https://www . geesforgeks . org/python-initialize-common-value-to-key/](https://www.geeksforgeeks.org/python-initialize-common-value-to-keys/)

有时，在使用 Python 时，我们可能会遇到一个问题，即我们需要为字典的每个键分配一个公共值。这种类型的问题不是偶然的，而是在编程时会出现很多次。让我们讨论执行这项任务的某些方法。

**方法一:使用`defaultdict()`+λ**

`defaultdict`可以使用默认为每个新键分配公共键的函数进行初始化。这是执行此任务的最推荐方式。

```py
# Python3 code to demonstrate working of
# Initialize common value to keys
# Using defaultdict()
from collections import defaultdict

# Initialize dictionary
test_dict = dict()

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Initialize common value to keys
# Using defaultdict()
res = defaultdict(lambda: 4, test_dict)
res_demo = res['Geeks']

# printing result
print("The value of key is :  " + str(res_demo))
```

**Output :**

```py
The original dictionary is : {}
The value of key is :  4

```

**方法 2:使用`get()` +默认值**

这个方法只是执行这个任务的一个显示黑客。它并不创建实际的列表，而只是打印传递给`get`函数的默认值以及结果。

```py
# Python3 code to demonstrate working of
# Initialize common value to keys
# Using get() + default value

# Initialize dictionary
test_dict = dict()

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Initialize common value to keys
# Using get() + default value
res_demo = test_dict.get('Geeks', 4)

# printing result
print("The value of key is :  " + str(res_demo))
```

**Output :**

```py
The original dictionary is : {}
The value of key is :  4

```