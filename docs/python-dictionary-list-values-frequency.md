# Python–字典列表值频率

> 原文:[https://www . geesforgeks . org/python-dictionary-list-values-frequency/](https://www.geeksforgeeks.org/python-dictionary-list-values-frequency/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要执行计算字典值列表中所有值的频率的任务。这是一个很常见的问题，在很多领域都有使用案例。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {1: ['gfg '，' CS '，' cool']，2: ['gfg '，' CS']}
> **输出** : {'gfg': 2，' CS': 2，' cool': 1}
> **输入** : test_dict = {1 : ['gfg '，' CS']}
> **输出** : {'gfg': 1，' CS': 1}

**方法#1:使用 defaultdict() + loop**
以上函数的组合可以用来解决这个问题。在这种情况下，我们使用 defaultdict()为每个值初始化计数器，并使用暴力来增加字典列表中的计数器。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Dictionary List Values Frequency
# Using loop + defaultdict()
from collections import defaultdict

# initializing dictionary
test_dict = {1 : ['gfg', 'best', 'geeks'],
             2 : ['gfg', 'CS'],
             3 : ['best', 'for', 'CS'],
             4 : ['test', 'ide', 'success'],
             5 : ['gfg', 'is', 'best']}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Dictionary List Values Frequency
# Using loop + defaultdict()
res = defaultdict(int)
for key, val in test_dict.items():
    for sub in val:
        res[sub] += 1

# printing result
print("Values Frequency : " + str(dict(res)))
```

**Output : **

原始字典:{1: ['gfg '，' best '，' geeks']，2: ['gfg '，' CS']，3: ['best '，' for '，' CS']，4: ['test '，' ide '，' success']，5: ['gfg '，' is '，' best']}
值频率:{'gfg': 3，' best': 3，' geeks': 1，' CS': 2，' for': 1，' test': 1，' ide': 1，' success ':1 }

**方法 2:使用 chain . from _ iterables()+Counter()**
以上函数的组合可以用来解决这个问题。在本文中，我们使用 Counter()执行计数任务，使用 from_iterables()完成值的展平/提取。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Dictionary List Values Frequency
# Using chain.from_iterables() + Counter()
from collections import Counter
from itertools import chain

# initializing dictionary
test_dict = {1 : ['gfg', 'best', 'geeks'],
             2 : ['gfg', 'CS'],
             3 : ['best', 'for', 'CS'],
             4 : ['test', 'ide', 'success'],
             5 : ['gfg', 'is', 'best']}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Dictionary List Values Frequency
# Using chain.from_iterables() + Counter()
res = Counter(chain.from_iterable(test_dict.values()))

# printing result
print("Values Frequency : " + str(dict(res)))
```

**Output : **

原始字典:{1: ['gfg '，' best '，' geeks']，2: ['gfg '，' CS']，3: ['best '，' for '，' CS']，4: ['test '，' ide '，' success']，5: ['gfg '，' is '，' best']}
值频率:{'gfg': 3，' best': 3，' geeks': 1，' CS': 2，' for': 1，' test': 1，' ide': 1，' success ':1 }