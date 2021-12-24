# Python–增量子列表总和

> 原文:[https://www . geesforgeks . org/python-incremental-sublist-sum/](https://www.geeksforgeeks.org/python-incremental-sublist-sum/)

有时我们需要对元素进行分组，分组的技术和要求也相应地有所不同。对元素进行分组的一种方法是通过列表中的第 I 个大小，该列表存储了带有后续大小 I 的求和值的索引键的字典。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`islice() + sum()` +字典理解**
切片方法可用于将需要制作的列表块分组为字典的值，然后使用字典理解将其分配给它们的指定索引键。sum()用于对创建的列表进行求和。

```
# Python3 code to demonstrate
# Incremental Sublist Sum
# using islice() + sum() + dictionary comprehension
from itertools import islice

# initializing list
test_list = [4, 7, 8, 10, 12, 15, 13, 17, 14, 5]

# printing original list 
print("The original list : " + str(test_list))

# using islice() + sum() + dictionary comprehension
# Incremental Sublist Sum
temp = iter(test_list)
res = {key: val for key, val in ((i, sum(list(islice(temp, i)))) for i in range(1, len(test_list))) if val}

# printing result
print("The Incremental Sublist Sum is : " + str(res))
```

**Output :**

```
The original list : [4, 7, 8, 10, 12, 15, 13, 17, 14, 5]
The Incremental Sublist Sum is : {1: 4, 2: 15, 3: 37, 4: 49}

```