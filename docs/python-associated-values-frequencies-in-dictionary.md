# Python–字典中的关联值频率

> 原文:[https://www . geesforgeks . org/python-associated-values-frequency-in-dictionary/](https://www.geeksforgeeks.org/python-associated-values-frequencies-in-dictionary/)

有时，在使用字典时，我们可能会遇到这样的问题:我们需要计算记录列表中与字典中每个值相关联的值。这种问题比较特殊，但在开发领域会有应用。让我们讨论执行这项任务的特定方式。

**方法:使用嵌套`defaultdict() + Counter()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用嵌套的 defaultdict 来跟踪元素，元素的计数由 Counter()完成。

```py
# Python3 code to demonstrate working of 
# Associated Values Frequencies in Dictionary
# Using defaultdict() + Counter()
from collections import defaultdict, Counter

# initializing list
test_list = [{'gfg' : 1, 'is' : 3, 'best' : 4},
             {'gfg' : 3, 'is' : 2, 'best' : 4}, 
             {'gfg' : 3, 'is' : 5, 'best' : 2},
             {'gfg' : 5, 'is' : 2, 'best' : 1},
             {'gfg' : 2, 'is' : 4, 'best' : 3},
             {'gfg' : 1, 'is' : 3, 'best' : 5},
             {'gfg' : 1, 'is' : 3, 'best' : 2}]

# printing original list
print("The original list is : " + str(test_list))

# Associated Values Frequencies in Dictionary
# Using defaultdict() + Counter()
res = defaultdict(Counter)
for sub in test_list:
    for key, val in sub.items():
        res[key][val] += 1

# printing result 
print("The list after Frequencies : " + str(dict(res))) 
```

**Output :**

> 原始列表为:[{'gfg': 1，' is': 3，' best': 4}，{'gfg': 3，' is': 2，' best': 4}，{'gfg': 3，' is': 5，' best': 2}，{'gfg': 2，' is': 4，' best': 3}，{'gfg': 1，' is': 3，' best': 5}，{'gfg': 1，' is': 3，' best': 2}]
> 频率后的列表::