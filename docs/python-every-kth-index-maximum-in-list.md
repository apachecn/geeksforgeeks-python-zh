# Python–列表中的每 Kth 索引最大值

> 原文:[https://www . geesforgeks . org/python-ever-kth-index-max-in-list/](https://www.geeksforgeeks.org/python-every-kth-index-maximum-in-list/)

我们通常希望对列表中的所有元素使用特定的函数。但是有时，根据需求，我们希望对列表中的某些元素使用特定的功能，基本上是对列表中的每个 Kth 元素。让我们讨论一些可以实现这些元素最大化的方法。

**方法一:使用列表理解+ `enumerate() + max()`**
获取列表每第 k 个数的功能可以借助列表理解来完成，枚举功能有助于整个列表的迭代。max()有助于找到 max。

```
# Python3 code to demonstrate
# Every Kth index Maximum in List
# using list comprehension + enumerate() + max()

# initializing list 
test_list = [1, 4, 5, 6, 7, 8, 9, 12]

# printing the original list
print ("The original list is : " + str(test_list))

# initializing K 
K = 3

# using list comprehension + enumerate() + max()
# Every Kth index Maximum in List
# max of every 3rd element
res = max([i for j, i in enumerate(test_list) if j % K == 0 ])

# printing result
print ("The max of every kth element : " + str(res))
```

**Output :**

```
The original list is : [1, 4, 5, 6, 7, 8, 9, 12]
The max of every kth element : 9

```