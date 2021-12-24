# Python |字典初始化用常用字典

> 原文:[https://www . geesforgeks . org/python-dictionary-initialization-with-common-dictionary/](https://www.geeksforgeeks.org/python-dictionary-initialization-with-common-dictionary/)

有时，在使用字典时，我们可能会有一个实用程序，其中我们需要用记录值初始化字典，以便以后可以修改它们。这种应用可能发生在一般或竞争性编程的记忆情况下。让我们讨论一下执行这项任务的具体方法。

**方法:使用`zip() + repeat()`**
这些功能的组合可以用来执行这个特定的任务。在这种情况下，借助于 zip()使用 repeat()将字典值附加到重复的键上

```
# Python3 code to demonstrate working of
# Dictionary initialization with common dictionary
# Using zip() + repeat()
from itertools import repeat

# initialization Dictionary 
test_dict = {'gfg' : 1, 'best' : 3}

# Using zip() + repeat()
# Dictionary initialization with common dictionary
res = dict(zip(range(4), repeat(test_dict)))

# printing result 
print("The dictionary with record values : " + str(res))
```

**Output :**

```
The dictionary with record values : {0: {'gfg': 1, 'best': 3}, 1: {'gfg': 1, 'best': 3}, 2: {'gfg': 1, 'best': 3}, 3: {'gfg': 1, 'best': 3}}

```