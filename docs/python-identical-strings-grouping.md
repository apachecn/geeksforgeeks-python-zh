# Python |相同字符串分组

> 原文:[https://www . geesforgeks . org/python-相同-字符串-分组/](https://www.geeksforgeeks.org/python-identical-strings-grouping/)

有时，我们需要执行传统的任务，将一些类似的字符串分组到一个单独的列表中，从而形成一个列表列表。这也有助于计数，并获得元素的排序顺序。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`collections.Counter()`**
这个特殊的函数可以证明对执行这个特殊的任务非常有用，因为它计算列表中字符串的频率，然后我们可以使用列表理解将它们配对。

```py
# Python3 code to demonstrate
# Identical Strings Grouping 
# using collections.Counter()
import collections

# initializing list 
test_list = ["Gfg", "best", "is", "Gfg", "is", "best", "Gfg", "best"]

# printing original list 
print("The original list : " + str(test_list))

# using collections.Counter()
# Identical Strings Grouping
temp = collections.Counter(test_list)
res = [[i] * j for i, j in temp.items()]

# print result
print("The Strings after grouping are : " + str(res))
```

**Output :**

```py
The original list : ['Gfg', 'best', 'is', 'Gfg', 'is', 'best', 'Gfg', 'best']
The Strings after grouping are : [['best', 'best', 'best'], ['Gfg', 'Gfg', 'Gfg'], ['is', 'is']]

```