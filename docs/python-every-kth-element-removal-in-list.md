# Python |列表中的每一个 Kth 元素移除

> 原文:[https://www . geesforgeks . org/python-ever-kth-element-remove-in-list/](https://www.geeksforgeeks.org/python-every-kth-element-removal-in-list/)

我们通常希望对列表中的所有元素使用特定的函数。但是有时，根据要求，我们希望删除列表中的某些元素，基本上是列表中的每个 Kth 元素。让我们讨论一下实现这一点的某些方法。

**方法一:使用列表理解+ `enumerate()`**
获取列表每第 k 个数的功能可以借助列表理解来完成，枚举功能有助于整个列表的迭代。

```
# Python3 code to demonstrate
# Every Kth element removal in List
# using list comprehension + enumerate()

# initializing list 
test_list = [1, 4, 5, 6, 7, 8, 9, 12]

# printing the original list
print ("The original list is : " + str(test_list))

# initializing K 
K = 3

# using list comprehension + enumerate()
# Every Kth element removal in List
# Remove every third element
res = [i for j, i in enumerate(test_list) if j % K != 0]

# printing result
print ("The list after removing every Kth element : " + str(res))
```

**Output :**

```
The original list is : [1, 4, 5, 6, 7, 8, 9, 12]
The list after removing every kth element : [4, 5, 7, 8, 12]

```