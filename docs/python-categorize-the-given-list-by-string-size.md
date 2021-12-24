# Python |按字符串大小给定列表分类

> 原文:[https://www . geesforgeks . org/python-按字符串大小对给定列表进行分类/](https://www.geeksforgeeks.org/python-categorize-the-given-list-by-string-size/)

有时，我们有一个用例，在这个用例中，我们需要通过各种因素对字符串进行分组，比如第一个字母或任何其他因素。这些类型的问题是数据库查询的典型问题，因此可能会在编程时出现在 web 开发中。本文重点介绍一种按字符串大小分组的方法。让我们讨论一下实现这一点的某些方法。

**方法一:使用`next()`+λ+循环**

上述 3 个函数的组合被用来通过朴素方法解决这个特殊问题。lambda 函数执行寻找相似长度的任务，next 函数有助于向前迭代。

```py
# Python3 code to demonstrate
# Categorize by string size 
# using next() + lambda + loop

# initializing list
test_list = ['man', 'a', 'geek', 'for', 'b', 'free']

# printing original list
print("The original list : " + str(test_list))

# using next() + lambda + loop
# Categorize by string size 
util_func = lambda x, y: len(x) == len(y)
res = []
for sub in test_list:
    ele = next((x for x in res if util_func(sub, x[0])), [])
    if ele == []:
        res.append(ele)
    ele.append(sub)

# print result
print("The list after Categorization : " + str(res))
```

**Output :**

```py
The original list : ['man', 'a', 'geek', 'for', 'b', 'free']
The list after Categorization : [['man', 'for'], ['a', 'b'], ['geek', 'free']]

```

**方法 2:使用`sorted() + groupby()`**

这个特殊的任务也可以使用 groupby 函数来解决，该函数提供了一种解决这个问题的方便方法。sorted 函数按大小对元素进行排序，以馈送到相关分组的 groupby。

```py
# Python3 code to demonstrate
# Categorize by string size 
# using sorted() + groupby()
from itertools import groupby

# initializing list
test_list = ['man', 'a', 'geek', 'for', 'b', 'free']

# printing original list
print("The original list : " + str(test_list))

# using sorted() + groupby()
# Categorize by string size 
util_func = lambda x: len(x)
temp = sorted(test_list, key = util_func)
res = [list(ele) for i, ele in groupby(temp, util_func)]

# print result
print("The list after Categorization : " + str(res))
```

**Output :**

```py
The original list : ['man', 'a', 'geek', 'for', 'b', 'free']
The list after Categorization : [['a', 'b'], ['man', 'for'], ['geek', 'free']]

```