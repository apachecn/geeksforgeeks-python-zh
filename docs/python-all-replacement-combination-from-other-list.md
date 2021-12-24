# Python–其他列表中的所有替换组合

> 原文:[https://www . geesforgeks . org/python-all-replacement-combination-from-other-list/](https://www.geeksforgeeks.org/python-all-replacement-combination-from-other-list/)

给定一个列表，任务是编写一个 Python 程序来执行从其他列表到当前列表的所有可能的替换。

> **输入** : test_list = [4，1，5]，repl_list = [8，10]
> **输出** : [(4，1，5)，(4，1，8)，(4，1，10)，(4，5，8)，(4，5，10)，(4，8，10)，(1，5，8)，(1，5，10)，(1，8，10)，(5，8，10)]
> **解释**:所有元素替换为 0 个以上
> 
> **输入** : test_list = [4，1]，repl_list = [8，10]
> **输出** : [(4，1)，(4，8)，(4，10)，(1，8)，(1，10)，(8，10)]
> **说明:**所有元素被第 2 个列表中的 0 个或 0 个以上的元素替换

**方法#1:使用** [**组合()**](https://www.geeksforgeeks.org/python-itertools-combinations-function/)**+**[**len()**](https://www.geeksforgeeks.org/python-ways-to-find-length-of-list/)

在这种情况下，我们使用*组合()*来执行构建合并列表的组合的任务，并且 *len()* 用于将输出的大小限制为初始列表的长度。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# All replacement combination from other list
# Using combinations() + len()
from itertools import combinations

# initializing list
test_list = [4, 1, 5]

# printing original list
print("The original list is : " + str(test_list))

# initializing replacement list
repl_list = [8, 10]

# using combinations() to get all combinations replacements
res = list(combinations(test_list + repl_list, len(test_list)))

# printing result
print("All combinations replacements from other list : " + str(res))
```

**输出:**

> 原列表为:[4，1，5]
> 其他列表中的所有组合替换:[(4，1，5)，(4，1，8)，(4，1，10)，(4，5，8)，(4，5，10)，(4，8，10)，(1，5，8)，(1，5，10)，(1，5，10)，(1，8，10)，(5，8，10)]

**方法 2:使用** [**组合()**](https://www.geeksforgeeks.org/python-itertools-combinations-function/) **+** [**延伸()**](https://www.geeksforgeeks.org/append-extend-python/)

在本例中，我们使用 extend()执行连接列表的任务，其余所有功能与上述方法类似。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# All replacement combination from other list
# Using combinations() + extend()
from itertools import combinations

# initializing list
test_list = [4, 1, 5]

# printing original list
print("The original list is : " + str(test_list))

# initializing replacement list 
repl_list = [8, 10]

# using combinations() to get all combinations replacements
# extend() for concatenation
n = len(test_list)
test_list.extend(repl_list)
res = list(combinations(test_list, n))

# printing result 
print("All combinations replacements from other list : " + str(res))
```

**输出:**

> 原列表为:[4，1，5]
> 其他列表中的所有组合替换:[(4，1，5)，(4，1，8)，(4，1，10)，(4，5，8)，(4，5，10)，(4，8，10)，(1，5，8)，(1，5，10)，(1，5，10)，(1，8，10)，(5，8，10)]