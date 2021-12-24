# Python–出现在多个字符串中的字符

> 原文:[https://www . geesforgeks . org/python-多字符串中出现的字符/](https://www.geeksforgeeks.org/python-characters-occurring-in-multiple-strings/)

有时，在使用 Python 字符串时，我们可能会遇到这样的问题，即我们需要在字符串列表中提取出现在多个字符串中的字符。这种问题通常发生在网络开发和数据科学领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用`Counter() + set()`**
这是可以执行此任务的方式之一。在这种情况下，我们检查所有字符串，计算每个字符串中的字符频率，并返回出现不止一个字符串的字符。

```
# Python3 code to demonstrate working of 
# Characters occurring in multiple Strings
# Using Counter() + set()
from itertools import chain
from collections import Counter

# initializing list
test_list = ['gfg', 'is', 'best', 'for', 'geeks', 'and', 'cs']

# printing original list
print("The original list is : " + str(test_list))

# Characters occurring in multiple Strings
# Using Counter() + set()
temp = (set(sub) for sub in test_list)
cntr = Counter(chain.from_iterable(temp))
res =  [chr for chr, count in cntr.items() if count >= 2]

# printing result 
print("Characters with Multiple String occurrence : " + str(res)) 
```

**Output :**

> 原始列表为:['gfg '，' is '，' best '，' for '，' geeks '，' cs']
> 出现多个字符串的字符:['g '，' e '，' f '，' s']