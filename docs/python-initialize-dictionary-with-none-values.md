# Python |用无值初始化字典

> 原文:[https://www . geesforgeks . org/python-initialize-dictionary-with-none-values/](https://www.geeksforgeeks.org/python-initialize-dictionary-with-none-values/)

有时，在使用字典时，我们可能会有一个实用程序，其中我们需要用 None 值初始化字典，以便以后可以修改它们。这种应用可能发生在一般或竞争性编程的记忆情况下。让我们讨论执行这项任务的某些方法。

**方法#1:使用`zip() + repeat()`**
这些功能的组合可用于执行该特定任务。在这种情况下，在`zip()`的帮助下，无值被附加到使用`repeat()`重复的键上

```py
# Python3 code to demonstrate working of
# Initialize dictionary with None values
# Using zip() + repeat()
from itertools import repeat

# Using zip() + repeat()
# Initialize dictionary with None values
res = dict(zip(range(10), repeat(None)))

# printing result 
print("The dictionary with None values : " + str(res))
```

**Output :**

> 无值字典:{0:无，1:无，2:无，3:无，4:无，5:无，6:无，7:无，8:无，9:无}