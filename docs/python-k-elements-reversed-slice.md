# Python–K 元素反向切片

> 原文:[https://www . geesforgeks . org/python-k-elements-reversed-slice/](https://www.geeksforgeeks.org/python-k-elements-reversed-slice/)

给定元素列表，执行 K 元素反向切片。

> **输入** : test_list = [2，4，6，8，3，9，12，15，16，18]，K = 3
> **输出**:【18，16，15】
> **解释**:后端切片的 3 个元素。
> 
> **输入**:test _ list =【2，4，6，8】，K = 3
> **输出**:【8，6，4】
> **解释** : 3 个元素从后端切片，8，6，4。

**方法#1:使用列表切片**

这是执行这项任务的方法之一。在这种情况下，我们使用列表切片的反向和负切片功能来执行反向切片。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# K elements Reversed Slice
# Using list slicing 

# initializing list
test_list = [2, 4, 6, 8, 3, 9, 12, 15, 16, 18]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 6

# using double slice to solve problem.
# "-" sign for slicing from rear 
res = test_list[-K:][::-1]

# printing result 
print("The sliced list : " + str(res))
```

**Output**

```py
The original list : [2, 4, 6, 8, 3, 9, 12, 15, 16, 18]
The sliced list : [18, 16, 15, 12, 9, 3]

```

**方法 2:使用 islice() + reversed()**

这是解决这个问题的功能方法。在本例中，我们使用 islice()执行切片，然后使用 reversed()反转列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# K elements Reversed Slice
# Using K elements Reversed Slice
from itertools import islice

# initializing list
test_list = [2, 4, 6, 8, 3, 9, 12, 15, 16, 18]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 6

# using revered and islice to slice 
# and then perform reverse
res = list(islice(reversed(test_list), K))

# printing result 
print("The sliced list : " + str(res))
```

**Output**

```py
The original list : [2, 4, 6, 8, 3, 9, 12, 15, 16, 18]
The sliced list : [18, 16, 15, 12, 9, 3]

```