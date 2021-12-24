# Python–从列表中的范围提取元素

> 原文:[https://www . geesforgeks . org/python-从列表范围中提取元素/](https://www.geeksforgeeks.org/python-extract-elements-from-ranges-in-list/)

给定一个列表和一个包含范围的元组列表，从列表中提取这些范围中的所有元素。

> **输入** : test_list = [4，5，4，6，7，5，4，5，6，10]，range_list = [(2，4)，(7，8)]
> **输出**:【4，6，7，5，6】
> **解释** : 4，6，7 是 idx 2，3，4 和 5 处的元素，idx 7，8 处的元素。
> 
> **输入** : test_list = [4，5，4，6，7，5，4，5，6，10]，range_list = [(2，6)]
> **输出**:【4，6，7，5，4】
> **解释**:提取 2-6 指标的元素。

**方法#1:使用循环+列表切片**

在这种情况下，我们使用列表切片和循环迭代提取每个范围，并继续将提取切片扩展到扩展列表。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract elements from Ranges in List
# Using loop + list slicing 

# initializing list
test_list = [4, 5, 4, 6, 7, 5, 4, 5, 4, 6, 4, 6, 9, 8]

# printing original list
print("The original list is : " + str(test_list))

# initializing ranges
range_list = [(2, 4), (7, 8), (10, 12)]

res = []
for ele in range_list:

    # extending ranges
    res.extend(test_list[ele[0] : ele[1] + 1])

# printing result 
print("Ranges elements : " + str(res))
```

**Output**

```
The original list is : [4, 5, 4, 6, 7, 5, 4, 5, 4, 6, 4, 6, 9, 8]
Ranges elements : [4, 6, 7, 5, 4, 4, 6, 9]

```

**方法 2:使用列表理解**

在这种情况下，我们使用与上述函数类似的方法，不同之处在于列表理解被用来以紧凑的形式解决这个问题。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract elements from Ranges in List
# Using list comprehension
from itertools import chain

# initializing list
test_list = [4, 5, 4, 6, 7, 5, 4, 5, 4, 6, 4, 6, 9, 8]

# printing original list
print("The original list is : " + str(test_list))

# initializing ranges
range_list = [(2, 4), (7, 8), (10, 12)]

# using one-liner to solve this problem
res = list(chain.from_iterable([test_list[ele[0] : ele[1] + 1] for ele in range_list]))

# printing result 
print("Ranges elements : " + str(res))
```

**Output**

```
The original list is : [4, 5, 4, 6, 7, 5, 4, 5, 4, 6, 4, 6, 9, 8]
Ranges elements : [4, 6, 7, 5, 4, 4, 6, 9]

```