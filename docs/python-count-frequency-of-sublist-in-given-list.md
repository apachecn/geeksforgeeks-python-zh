# Python–统计给定列表中子列表的频率

> 原文:[https://www . geesforgeks . org/python-给定列表中子列表的计数频率/](https://www.geeksforgeeks.org/python-count-frequency-of-sublist-in-given-list/)

给定一个列表和一个子列表，计算列表中子列表的出现次数。

> **输入** : test_list = [4，5，3，5，7，8，3，5，7，2，3，5，7]，子列表= [3，5，7]
> **输出** : 3
> **解释** : 3，5，7 出现 3 次。
> 
> **输入** : test_list = [4，5，3，5，8，8，3，2，7，2，3，6，7]，子列表= [3，5，7]
> **输出** : 0
> **解释**:未发现出现。

**方法一:使用列表理解+切片**

在这种情况下，我们对使用切片提取的列表的每个子列表进行测试，如果找到，则将元素添加到列表中，最后使用 len()计算列表的长度。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sublist Frequency
# Using list comprehension + slicing 

# initializing list
test_list = [4, 5, 3, 5, 7, 8, 3, 5, 7, 2, 7, 3, 2]

# printing original list
print("The original list is : " + str(test_list))

# initializing Sublist
sublist = [3, 5, 7]

# slicing is used to extract chunks and compare
res = len([sublist for idx in range(len(test_list)) if test_list[idx : idx + len(sublist)] == sublist])

# printing result 
print("The sublist count : " + str(res))
```

**Output**

```py
The original list is : [4, 5, 3, 5, 7, 8, 3, 5, 7, 2, 7, 3, 2]
The sublist count : 2

```

**方法 2:使用 zip _ long()+islice()+all()+循环**

在本例中，我们使用 islice()执行切片任务，并使用 all()检查每个元素是否匹配，zip _ longest()有助于映射元素以检查子列表中的相等性。循环用于获取与列表中子列表第一个元素的索引匹配，以提高效率。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sublist Frequency
# Using zip_longest() + islice() + all() + loop 
from itertools import zip_longest, islice

# initializing list
test_list = [4, 5, 3, 5, 7, 8, 3, 5, 7, 2, 7, 3, 2]

# printing original list
print("The original list is : " + str(test_list))

# initializing Sublist
sublist = [3, 5, 7]

# slicing is used to extract chunks and compare
res = []
idx = 0  
while True:
    try:

        # getting to the index
        idx = test_list.index(sublist[0], idx)
    except ValueError:
        break

    # using all() to check for all elements equivalence
    if all(x == y for (x, y) in zip_longest(sublist, islice(test_list, idx, idx + len(sublist)))):
        res.append(sublist)
        idx += len(sublist)
    idx += 1

res = len(res)

# printing result 
print("The sublist count : " + str(res))
```

**Output**

```py
The original list is : [4, 5, 3, 5, 7, 8, 3, 5, 7, 2, 7, 3, 2]
The sublist count : 2

```