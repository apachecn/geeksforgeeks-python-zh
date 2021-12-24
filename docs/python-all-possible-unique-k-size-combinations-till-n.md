# Python–所有可能的唯一 K 尺寸组合，直到 N

> 原文:[https://www . geesforgeks . org/python-所有可能-唯一-k-size-组合-till-n/](https://www.geeksforgeeks.org/python-all-possible-unique-k-size-combinations-till-n/)

有时，在使用 Python 域时，我们可能会遇到一个问题，即我们需要生成各种元素的组合。这个问题可以在数据域和学校编程中得到应用。让我们讨论执行这项任务的某些方法。

> **输入** : N = 2，K = 3
> **输出** : [(0，0，0，1)，(0，1，1)，(1，1，1)]
> 
> **输入** : N = 4，K = 2
> **输出** : [(0，0)，(0，1)，(0，2)，(0，3)，(1，1)，(1，2)，(1，3)，(2，2)，(2，3)，(3，3)]

**方法#1:使用`product() + setdefault()` +循环**
上述功能的组合提供了解决这个问题的方法。在本文中，我们使用 product 执行所有组合，并使用 setdefault()和强力循环方法消除重复。

```
# Python3 code to demonstrate working of 
# All Possible unique K size combinations till N
# Using product() + setdefault() + loop
from itertools import product

# initializing N
N = 4

# Initialize K
K = 3

# All Possible unique K size combinations till N
# Using product() + setdefault() + loop
temp = list(product(range(N), repeat = K))
res = {}
for tup in temp:
    key = tuple(sorted(tup))
    res.setdefault(key, []).append(tup)
res = list(res.keys())

# printing result 
print("The unique combinations : " + str(res)) 
```

**Output :**

> 唯一的组合:[(0，0，0)，(0，0，1)，(0，0，2)，(0，0，3)，(0，1，1)，(0，1，2)，(0，1，3)，(0，2，2)，(0，2，3)，(0，3，3)，(1，1，1)，(1，1，2)，(1，1，3)，(1，2，2)，(1，2，3)，(1，3，3)，(2，2，2，3)，(2，2，2，3)，(2，3，3，3，3，3)

**方法 2:使用`combinations_with_replacement()`**
这为解决这个问题提供了一个替代方法。该功能在内部执行，这是获得解决方案所需的全部功能。

```
# Python3 code to demonstrate working of 
# All Possible unique K size combinations till N
# Using combinations_with_replacement()
from itertools import product, combinations_with_replacement

# initializing N
N = 4

# Initialize K
K = 3

# All Possible unique K size combinations till N
# Using combinations_with_replacement()
res = list(combinations_with_replacement(range(N), K))

# printing result 
print("The unique combinations : " + str(res)) 
```

**Output :**

> 唯一的组合:[(0，0，0)，(0，0，1)，(0，0，2)，(0，0，3)，(0，1，1)，(0，1，2)，(0，1，3)，(0，2，2)，(0，2，3)，(0，3，3)，(1，1，1)，(1，1，2)，(1，1，3)，(1，2，2)，(1，2，3)，(1，3，3)，(2，2，2，3)，(2，2，2，3)，(2，3，3，3，3，3)