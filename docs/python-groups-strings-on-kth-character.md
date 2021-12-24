# Python–将字符串分组到第 Kth 个字符上

> 原文:[https://www . geesforgeks . org/python-group-strings-on-kth-character/](https://www.geeksforgeeks.org/python-groups-strings-on-kth-character/)

有时，在使用 Python 字符串时，我们可能会遇到一个问题，即我们需要根据 Python 字符串的第 k 个字符对其进行分组。这种问题会出现在日常编程中。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是执行该任务的一种方式。在这种情况下，我们使用暴力方法执行分组任务。我们迭代每个字符串，并在条件检查后使用条件语句对字典进行分组。

```py
# Python3 code to demonstrate working of 
# Groups Strings on Kth character
# Using loop
from collections import defaultdict

# initializing list
test_list = ["gfg", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 2

# Groups Strings on Kth character
# Using loop
res = defaultdict(list)
for word in test_list:
    res[word[K - 1]].append(word)

# printing result 
print("The strings grouping : " + str(dict(res))) 
```

**Output :**

> 原始列表为:['gfg '，' is '，' best '，' for '，' geeks']
> 字符串分组:{'f': ['gfg']，' s': ['is']，' e': ['best '，' geeks']，' o': ['for']}