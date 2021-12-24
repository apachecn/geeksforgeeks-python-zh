# Python |从元组列表中查找前 K 个频繁元素

> 原文:[https://www . geesforgeks . org/python-find-top-k-frequency-elements-from-list-of-tuples/](https://www.geeksforgeeks.org/python-find-top-k-frequent-elements-from-a-list-of-tuples/)

给定一个以单词为第一元素，以其频率为第二元素的元组列表，任务是找到顶部 *k* 频繁元素。

下面是上面实现上述任务的一些方法。

**方法#1:使用`defaultdict`**

```py
# Python code to find top 'k' frequent element

# Importing
import collections
from operator import itemgetter
from itertools import chain

# Input list initialization
Input =[[('Name', 151)], [('ACe', 400)],
        [('TURN', 210)], [('RED', 1113)],
        [('YELLOW', 1)]]

# K initialization
K = 3

# Using defaultdict to  find top 'k' frequent element
dict_ = collections.defaultdict(list)
new_list = list(chain.from_iterable(Input))

for elem in new_list:
    dict_[elem[0]].append(elem[1])

res = {k: sum(v) for k, v in dict_.items()}

# Using sorted
Output = sorted(res.items(), key = itemgetter(1),
                             reverse = True)[0:K]

# printing output
print("Initial List of tuple is", Input)
print("\nTop 'K' elements are", Output)
```

**Output:**

> 元组的初始列表是[[('Name '，151)]，[('ACe '，400)]，[('TURN '，210)]，[('RED '，1113)]，[('YELLOW '，1)]
> 
> Top 'K '元素为[('RED '，1113)、(' ACe '，400)、(' TURN '，210)]

**方法二:使用`itertools` `sorted`**

```py
# Python code to find top 'k' frequent element
from operator import itemgetter
from itertools import chain

# Input list initialization
Input =[[('Name', 151)], [('ACe', 400)],
        [('TURN', 210)], [('RED', 1113)],
        [('YELLOW', 1)]]

# k initialization
K = 3

# Finding top 'k' frequent element 
# without using collection
Output = sorted(list(chain.from_iterable(Input)),
        key = itemgetter(1), reverse = True)[0:K]

# Printing Output
print("Initial List of tuple is", Input)
print("\nTop 'K' elements are", Output)
```

**Output:**

> 元组的初始列表是[[('Name '，151)]，[('ACe '，400)]，[('TURN '，210)]，[('RED '，1113)]，[('YELLOW '，1)]
> 
> Top 'K '元素为[('RED '，1113)、(' ACe '，400)、(' TURN '，210)]