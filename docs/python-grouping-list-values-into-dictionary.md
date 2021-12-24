# Python |将列表值分组到字典中

> 原文:[https://www . geesforgeks . org/python-group-list-values-in-dictionary/](https://www.geeksforgeeks.org/python-grouping-list-values-into-dictionary/)

有时，在处理数据时，我们可能会遇到这样的情况:我们有一个列表，我们需要用列表中的公共初始元素对它的第二个索引进行分组。让我们讨论一下解决这个问题的方法。

**方法:使用`defaultdict()` +循环+`dict()`+T3】**

defaultdict 可用于初始化组元素，loop 可用于将值组合在一起，并可使用`dict()`转换为字典。

```
# Python3 code to demonstrate working of
# Grouping list values into dictionary
# Using defaultdict() + loop + dict()
from collections import defaultdict

# initializing list
test_list = [['Gfg', 1], ['Gfg', 2], ['is', 3], ['best', 4], ['is', 5]]

# printing original list
print("The original list is : " + str(test_list))

# Grouping list values into dictionary
# Using defaultdict() + loop + dict()
temp = defaultdict(list)
for key, val in test_list:
    temp[key].append(val)
res = dict((key, tuple(val)) for key, val in temp.items())

# printing result
print("The grouped dictionary is :  " + str(res))
```

**输出:**

```
The original list is : [['Gfg', 1], ['Gfg', 2], ['is', 3], ['best', 4], ['is', 5]]
The grouped dictionary is :  {'Gfg': (1, 2), 'best': (4, ), 'is': (3, 5)}

```