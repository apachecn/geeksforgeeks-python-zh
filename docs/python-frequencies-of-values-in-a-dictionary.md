# Python–字典中值的频率

> 原文:[https://www . geesforgeks . org/python-字典中值的频率/](https://www.geeksforgeeks.org/python-frequencies-of-values-in-a-dictionary/)

有时，在使用 python 字典时，我们可能会遇到一个问题，即我们需要提取字典中值的频率。这是一个非常常见的问题，在许多领域都有应用，包括 web 开发和日常编程。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {'ide' : 3，' Gfg' : 3，' code' : 2}
> **输出** : {3: 2，2: 1}
> 
> **输入** : test_dict = {10 : 1，20 : 2，30 : 1，40 : 2 }
> **输出** : {1 : 2，2 : 2}

**方法一:使用`defaultdict()` +循环**
以上功能的组合可以解决这个问题。在这种情况下，我们使用 defaultdict()用整数初始化计数器字典，并使用循环以暴力方式增加计数器。

```
# Python3 code to demonstrate working of 
# Dictionary Values Frequency
# Using defaultdict() + loop
from collections import defaultdict

# initializing dictionary
test_dict = {'ide' : 3, 'Gfg' : 3, 'code' : 2}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Dictionary Values Frequency
# Using defaultdict() + loop
res = defaultdict(int)
for key, val in test_dict.items():
    res[val] += 1

# printing result 
print("The frequency dictionary : " + str(dict(res))) 
```

**Output:**

```
The original dictionary : {'Gfg': 3, 'code': 2, 'ide': 3}
The frequency dictionary : {2: 1, 3: 2}

```

**方法 2:使用`Counter() + values()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 values()执行值提取任务，使用 counter()执行频率计数器提取任务。

```
# Python3 code to demonstrate working of 
# Dictionary Values Frequency
# Using Counter() + values()
from collections import Counter

# initializing dictionary
test_dict = {'ide' : 3, 'Gfg' : 3, 'code' : 2}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Dictionary Values Frequency
# Using defaultdict() + loop
res = Counter(test_dict.values())

# printing result 
print("The frequency dictionary : " + str(dict(res))) 
```

**Output:**

```
The original dictionary : {'code': 2, 'Gfg': 3, 'ide': 3}
The frequency dictionary : {2: 1, 3: 2}

```