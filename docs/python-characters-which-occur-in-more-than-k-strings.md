# Python–出现在 K 个以上字符串中的字符

> 原文:[https://www . geesforgeks . org/python-出现在 k 个以上字符串中的字符/](https://www.geeksforgeeks.org/python-characters-which-occur-in-more-than-k-strings/)

有时，在使用 Python 时，我们会遇到一个问题，即我们计算字符串中有多少字符。但是有时候，我们会遇到一个问题，我们需要获取所有出现在快速 K 字符串中的字符。让我们讨论执行这项任务的某些方法。

**方法#1:使用`set() + Counter() + items() + loop`**
上述功能的组合可用于执行该特定任务。在这种情况下，我们发现计数使用计数器和设置是用来限制字符重复。

```py
# Python3 code to demonstrate 
# Characters which Occur in More than K Strings
# using set() + Counter() + loop + items()
from collections import Counter
from itertools import chain

def char_ex(strs, k):
    temp = (set(sub) for sub in strs)
    counts = Counter(chain.from_iterable(temp))
    return {chr for chr, count in counts.items() if count >= k}

# Initializing list
test_list = ['Gfg', 'ise', 'for', 'Geeks']

# printing original list
print("The original list is : " + str(test_list))

# Initializing K
K = 2

# Characters which Occur in More than K Strings
# using set() + Counter() + loop + items()
res = char_ex(test_list, K)

# printing result 
print ("Filtered Characters are : " + str(res))
```

**Output :**

```py
The original list is : ['Gfg', 'ise', 'for', 'Geeks']
Filtered Characters are : {'e', 'G', 's', 'f'}

```