# Python–查找特定键的每个值的出现次数

> 原文:[https://www . geesforgeks . org/python-查找特定键的每个值的出现次数/](https://www.geeksforgeeks.org/python-find-occurrences-for-each-value-of-a-particular-key/)

给定一个特定键的字典列表，找出该键的每个值的出现次数。

> **输入** : test_list = [{'gfg' : 3，' best' : 4}，{'gfg' : 3，' best' : 5}，
> {'gfg' : 4，' best' : 4}，{'gfg' : 7，' best' : 4} ]，K = 'gfg'
> **输出** : [{3: 2}，{4: 1}，{7: 1}]
> **解释** : gfg 有 2 次出现 3 个 as 值。
> 
> **输入** : test_list = [{'gfg' : 3，' best' : 4}，{'gfg' : 3，' best' : 5}，
> {'gfg' : 4，' best' : 4}，{'gfg' : 7，' best' : 4} ]，K = 'best'
> **输出** : [{4: 3}，{5: 1}]
> **解释** : best 有 3 次出现 4 个 as 值。

**方法一:使用**[**group by()**](https://www.geeksforgeeks.org/pandas-groupby/)**+词典理解**

在这种情况下，我们使用 groupby()对键的值进行分组，并使用字典理解和 [len()](https://www.geeksforgeeks.org/list-methods-in-python-set-1-in-not-in-len-min-max/) 组装和提取值频率。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Values Frequency grouping of K in dictionaries
# Using groupby() + dictionary comprehension
from itertools import groupby

# initializing list
test_list = [{'gfg' : 3, 'best' : 4}, {'gfg' : 3, 'best' : 5}, 
             {'gfg' : 4, 'best' : 4}, {'gfg' : 7, 'best' : 4} ]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 'gfg'

# groupby() used to group values and len() to compute Frequency
res = [{key: len(list(val))} for key, val in groupby(test_list, lambda sub: sub[K])]

# printing result 
print("The Values Frequency : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': 3，' best': 4}，{'gfg': 3，' best': 5}，{'gfg': 4，' best': 4}，
> {'gfg': 7，' best': 4}]
> 值频率:[{3: 2}，{4: 1}，{7: 1}]

**方法 2:使用** [**计数器()**](https://www.geeksforgeeks.org/counters-in-python-set-1/)

在这种情况下，执行频率检查的任务是使用计数器()完成的。在单个字典中返回结果。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Values Frequency grouping of K in dictionaries
# Using Counter()
from collections import Counter

# initializing list
test_list = [{'gfg' : 3, 'best' : 4}, {'gfg' : 3, 'best' : 5}, 
             {'gfg' : 4, 'best' : 4}, {'gfg' : 7, 'best' : 4} ]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 'gfg'

# groupby() used to group values and len() to compute Frequency
res = dict(Counter(sub[K] for sub in test_list))

# printing result 
print("The Values Frequency : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': 3，' best': 4}，{'gfg': 3，' best': 5}，{'gfg': 4，' best': 4}，
> {'gfg': 7，' best': 4}]
> 值频率:[{3: 2}，{4: 1}，{7: 1}]