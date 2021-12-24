# Python |获取匹配指数

> 原文:[https://www.geeksforgeeks.org/python-get-match-indices/](https://www.geeksforgeeks.org/python-get-match-indices/)

有时候，在处理列表时，我们需要处理两个列表并搜索匹配项，然后只返回匹配项的索引。当主列表的大小非常大时，查询整个列表进行这个过程是不可行的，因此只有匹配索引有助于这个原因。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `index()`**
这个问题可以通过使用 python 的索引函数来获得想要的索引来潜在地解决，并且列表理解可以用来将其扩展到整个字符串。

```py
# Python3 code to demonstrate
# Get match indices
# using list comprehension and index()

# initializing lists
test_list1 = [5, 4, 1, 3, 2]
test_list2 = [1, 2]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# using list comprehension and index()
# Get match indices
res = [test_list1.index(i) for i in test_list2]

# print result
print("The Match indices list is : " + str(res))
```

**Output :**

```py
The original list 1 : [5, 4, 1, 3, 2]
The original list 2 : [1, 2]
The Match indices list is : [2, 4]

```