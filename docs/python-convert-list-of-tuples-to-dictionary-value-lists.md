# Python |将元组列表转换为字典值列表

> 原文:[https://www . geesforgeks . org/python-convert-list-of-tuples-to-dictionary-value-list/](https://www.geeksforgeeks.org/python-convert-list-of-tuples-to-dictionary-value-lists/)

python 中数据类型相互转换的一个问题是元组列表到字典的转换，其中键是元组的第一个元素，在字典中唯一标识为键，其对应值作为元组的第二个元素作为各个键的对应值列表。让我们讨论如何解决这个特殊的问题。

**方法#1:使用 defaultdict() +循环**
使用 defaultdict()和循环可以轻松解决这个问题。defaultdict 提供了一个缺省值字典容器来为键分配相应的值列表，这样我们就不需要用空列表来初始化键，循环用于从元组中提取相似的值。

```py
# Python3 code to demonstrate working of
# Convert list of tuples to dictionary value lists
# Using defaultdict() + loop
from collections import defaultdict

# initializing list
test_list = [(1, 'gfg'), (1, 'is'), (2, 'best'), (3, 'for'), (4, 'CS')]

# printing original list
print("The original list is : " + str(test_list))

# Using defaultdict() + loop
# Convert list of tuples to dictionary value lists
res = defaultdict(list)
for i, j in test_list:
    res[i].append(j)

# printing result 
print("The merged dictionary is : " + str(dict(res)))
```

**Output :**

> 原始列表为:[(1，' gfg ')，(1，' is ')，(2，' best ')，(3，' for ')，(4，' CS')]
> 合并字典为:{1: ['gfg '，' is']，2: ['best']，3: ['for']，4: ['CS']}