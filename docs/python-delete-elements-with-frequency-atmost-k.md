# Python |删除频率为 K 的元素

> 原文:[https://www . geesforgeks . org/python-delete-elements-with-frequency-Atmos-k/](https://www.geeksforgeeks.org/python-delete-elements-with-frequency-atmost-k/)

有许多方法可以用来执行列表中的删除。无论是删除功能，弹出功能和许多其他功能。但大多数时候，我们通常不会处理简单的删除，而是有一定的限制。本文讨论了某些方法，在这些方法中，我们可以只删除那些出现次数少于 K 次的元素。

**方法#1:使用列表理解+ `count()`**
这里应用的思想是使用列表理解构建一个新的列表，并且只插入那些出现 K 次以上的元素。计数操作是在计数功能的帮助下完成的。

```py
# Python3 code to demonstrate
# remove elements less than and equal K 
# using list comprehension + count()

# initializing list
test_list = [1, 4, 3, 2, 3, 3, 2, 2, 2, 1]

# printing original list
print("The original list : " + str(test_list))

# initializing K
K = 2

# using list comprehension + count()
# remove elements less than K 
res = [ i for i in test_list if test_list.count(i) > K]

# print result
print("The list removing elements less than and equal K  : " + str(res))
```

**Output :**

```py
The original list : [1, 4, 3, 2, 3, 3, 2, 2, 2, 1]
The list removing elements less than and equal K  : [3, 2, 3, 3, 2, 2, 2]

```