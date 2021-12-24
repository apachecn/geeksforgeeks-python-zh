# Python |给定数字列表中可能的最大数字

> 原文:[https://www . geesforgeks . org/python-给定数字列表中最大可能数字/](https://www.geeksforgeeks.org/python-largest-number-possible-from-list-of-given-numbers/)

给定一个数字列表，任务是从列表中给出的元素中找到最大可能的数字。

从竞争的角度来看，这是一个至关重要的问题，本文讨论了 Python 中解决这个问题的各种方法。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用 `sorted() + lambda`**
以上功能的组合可以用来执行此任务。sorted 函数执行转换为字符串的列表索引的反向排序，lambda 函数处理转换和迭代操作。

```py
# Python code to demonstrate 
# largest possible number in list
# using sorted() + lambda
from functools import cmp_to_key

# initializing list 
test_list = [23, 65, 98, 3, 4]

# printing original list
print ("The original list is : " + str(test_list))

# using sorted() + lambda
# largest possible number in list 
res = sorted(test_list, key = cmp_to_key(lambda i, j: -1 
                if str(j) + str(i) < str(i) + str(j) else 1))

# printing result 
print ("The largest possible number : " + ''.join(map(str,res)))
```

**Output:**

```py
The original list is : [23, 65, 98, 3, 4]
The largest possible number : 98654323

```

**方法 2:使用`itertools.permutation()`+`join() + max()`**
ITER tools . replacement 可用于获得可能的置换，max 函数根据 join 函数给出的连接输出将其转换为整数后选择其中的最大值。

```py
# Python3 code to demonstrate 
# largest possible number in list
# using itertools.permutation() + join() + max()
from itertools import permutations

# initializing list 
test_list = [23, 65, 98, 3, 4]

# printing original list
print ("The original list is : " + str(test_list))

# using itertools.permutation() + join() + max()
# largest possible number in list 
res = int(max((''.join(i) for i in permutations(str(i) 
                     for i in test_list)), key = int))

# printing result 
print ("The largest possible number : " +  str(res))
```

**Output:**

```py
The original list is : [23, 65, 98, 3, 4]
The largest possible number : 98654323

```