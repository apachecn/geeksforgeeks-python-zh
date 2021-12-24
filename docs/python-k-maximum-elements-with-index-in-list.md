# Python–列表中带索引的 K 个最大元素

> 原文:[https://www . geesforgeks . org/python-k-列表中带索引的最大元素/](https://www.geeksforgeeks.org/python-k-maximum-elements-with-index-in-list/)

给定一个列表，提取 K 个最大元素及其索引。

> **输入** : test_list = [5，3，1，4，7，8，2]，K = 2
> **输出** : [(4，7)，(5，8)]
> **解释** : 8 在索引 5 上最大，4 上 7。
> 
> **输入** : test_list = [5，3，1，4，7，10，2]，K = 1
> **输出** : [(5，10)]
> **解释** : 10 在索引 5 上最大。

**方法#1:使用排序的()+索引()**

上述功能的结合提供了一种解决这个问题的方法。在这种情况下，我们首先执行排序并提取 K 个最大元素，然后将其封装在元组中，其顺序在原始列表中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# K Maximum elements with Index in List
# Using sorted() + index()

# initializing list
test_list = [5, 3, 1, 4, 7, 8, 2]

# printing original list 
print("The original list : " + str(test_list))

# initializing K
K = 3

# Using sorted() + index()
# using sorted() to sort and slice K maximum elements 
temp = sorted(test_list)[-K:]
res = []
for ele in temp:

    # encapsulating elements with index using index()
    res.append((test_list.index(ele), ele))

# printing result 
print("K Maximum with indices : " + str(res))
```

**Output**

```py
The original list : [5, 3, 1, 4, 7, 8, 2]
K Maximum with indices : [(0, 5), (4, 7), (5, 8)]

```

**方法 2:使用 enumerate() + itemgetter()**

上述功能的组合可以用来解决这个问题。在本例中，我们使用 enumerate()执行获取索引的任务，itemgetter()用于获取元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# K Maximum elements with Index in List
# Using enumerate() + itemgetter()
from operator import itemgetter

# initializing list
test_list = [5, 3, 1, 4, 7, 8, 2]

# printing original list
print("The original list : " + str(test_list))

# initializing K
K = 3

# Using enumerate() + itemgetter()
# Making index values pairs at 1st stage
res = list(sorted(enumerate(test_list), key = itemgetter(1)))[-K:]

# printing result
print("K Maximum with indices : " + str(res))
```

**Output**

```py
The original list : [5, 3, 1, 4, 7, 8, 2]
K Maximum with indices : [(0, 5), (4, 7), (5, 8)]

```