# Python–值列表的组合键

> 原文:[https://www . geesforgeks . org/python-group-key-to-value-list/](https://www.geeksforgeeks.org/python-group-keys-to-values-list/)

有时候，在使用 Python 字典时，我们可能会遇到这样的问题:我们需要找到字典中所有键的所有可能值。这个实用程序很常见，可以出现在许多领域，包括日常编程和学校编程。让我们讨论执行这项任务的特定方式。

**方法#1:使用循环+ `defaultdict()`**
上述功能的组合可用于执行该任务。在这种情况下，我们通过用列表数据类型初始化 defaultdict 来捕获列表中的所有元素，并继续将所有值附加到关联的键上。

```
# Python3 code to demonstrate working of 
# Group keys to values list
# Using loop + defaultdict()
from collections import defaultdict

# initializing list
test_list = [{'gfg' : 1, 'is' : 4, 'best' : 7}, 
             {'gfg' : 9, 'is' : 8, 'best' : 3},
             {'gfg' : 4, 'is' : 4, 'best' : 7},
             {'gfg' : 7, 'is' : 2, 'best' : 8},
             {'gfg' : 1, 'is' : 4, 'best' : 7},
             {'gfg' : 10, 'is' : 9, 'best' : 2},
             {'gfg' : 0, 'is' : 5, 'best' : 6}]

# printing original list
print("The original list is : " + str(test_list))

# Group keys to values list
# Using loop + defaultdict()
res = defaultdict(set)
for sub in test_list:
    for key, val in sub.items():
        res[key].add(val)

# printing result 
print("The grouped key values : " + str(dict(res))) 
```

**Output :**

> 原始列表为:[{'best': 7，' gfg': 1，' is': 4}，{'best': 3，' gfg': 9，' is': 8}，{'best': 7，' gfg ':4 }，{'best': 8，' gfg': 7，' is': 2}，{'best': 7，' gfg': 1，' is': 4}，{'best': 2，' gfg': 10，' is': 9}，{'best': 6，' gfg': 0，' is': 5}]
> 分组的键值