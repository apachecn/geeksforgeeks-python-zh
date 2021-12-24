# Python–将嵌套字典转换为映射元组

> 原文:[https://www . geesforgeks . org/python-convert-nested-dictionary-to-mapped-tuple/](https://www.geeksforgeeks.org/python-convert-nested-dictionary-to-mapped-tuple/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要将嵌套字典转换为映射元组。这种问题可能发生在网页开发和日常编程中。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {'gfg' : {'x' : 5，' y' : 6，' z': 3}，' best' : {'x' : 8，' y' : 3，' z': 5}}
> **输出** : [('x '，(5，8))，(' y '，(6，3))，(' z '，(3，5))]
> 
> **输入** : test_dict = {'gfg' : {'x' : 5，' y' : 6，' z': 3}}
> **输出** : [('x '，(5)，)，(' y '，(6)，)，(' z '，(3，)]

**方法#1:使用列表理解+生成器表达式**
以上函数的组合可以用来解决这个问题。在本文中，我们使用列表理解来执行创建元组的任务，生成器表达式通过使用 values()提取值来帮助分组。

```
# Python3 code to demonstrate working of 
# Convert Nested dictionary to Mapped Tuple
# Using list comprehension + generator expression

# initializing dictionary
test_dict = {'gfg' : {'x' : 5, 'y' : 6}, 'is' : {'x' : 1, 'y' : 4},
                                      'best' : {'x' : 8, 'y' : 3}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Convert Nested dictionary to Mapped Tuple
# Using list comprehension + generator expression
res = [(key, tuple(sub[key] for sub in test_dict.values())) 
                               for key in test_dict['gfg']]

# printing result 
print("The grouped dictionary : " + str(res)) 
```

**Output :**

> 原始字典为:{'gfg': {'x': 5，' y': 6}，' is': {'x': 1，' y': 4}，' best': {'x': 8，' y': 3}}
> 分组字典:[('x '，(5，1，8))，(' y '，(6，4，3))]

**方法 2:使用`defaultdict()` +循环**
这是可以执行该任务的另一种方式。在本文中，我们使用 defaultdict()执行嵌套字典的键的映射任务，并使用循环重新创建值列表。这种方法对于旧版本的 Python 很有用。

```
# Python3 code to demonstrate working of 
# Convert Nested dictionary to Mapped Tuple
# Using defaultdict() + loop
from collections import defaultdict    

# initializing dictionary
test_dict = {'gfg' : {'x' : 5, 'y' : 6}, 'is' : {'x' : 1, 'y' : 4}, 
                                      'best' : {'x' : 8, 'y' : 3}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Convert Nested dictionary to Mapped Tuple
# Using defaultdict() + loop
res = defaultdict(tuple)
for key, val in test_dict.items():
    for ele in val:
        res[ele] += (val[ele], )

# printing result 
print("The grouped dictionary : " + str(list(res.items())) 
```

**Output :**

> 原始字典为:{'gfg': {'x': 5，' y': 6}，' is': {'x': 1，' y': 4}，' best': {'x': 8，' y': 3}}
> 分组字典:[('x '，(5，1，8))，(' y '，(6，4，3))]