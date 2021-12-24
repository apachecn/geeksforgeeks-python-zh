# Python–将元组列表转换为字典，关键字来自给定的起始值

> 原文:[https://www . geesforgeks . org/python-convert-tuple-list-to-dictionary-with-key-from-给定-start-value/](https://www.geeksforgeeks.org/python-convert-tuple-list-to-dictionary-with-key-from-a-given-start-value/)

给定一个元组列表，下面的文章重点介绍如何将其转换为字典，键从指定的起始值开始。这个起始值只是给一个头开始，下一个键将增加它们的前一个键的值。

> **输入** : test_list = [(4，5)，(1，3)，(9，4)，(8，2)，(10，1)]，start = 4
> **输出** : {4: (4，5)，5: (1，3)，6: (9，4)，7: (8，2)，8: (10，1)}
> **解释**:元组索引起始键计数从 4 开始。
> **输入** : test_list = [(4，5)，(1，3)，(9，4)，(8，2)，(10，1)]，start = 6
> **输出** : {6: (4，5)，7: (1，3)，8: (9，4)，9: (8，2)，10: (10，1)}
> **解释**:从 6 开始索引的元组起始键计数。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，我们通过迭代每个元组并从开始添加其位置索引来构建字典，作为字典中的键值对。

## 蟒蛇 3

```py
# initializing list
test_list = [(4, 5), (1, 3), (9, 4), (8, 2), (10, 1)]

# printing original list
print("The original list is : " + str(test_list))

# initializing start
start = 4

res = dict()
for sub in test_list:

    # assigning positional index
    res[start] = sub
    start += 1

# printing result
print("Constructed dictionary : " + str(res))
```

**输出:**

> 原清单为:[(4，5)，(1，3)，(9，4)，(8，2)，(10，1)]
> 
> 构造字典:{4: (4，5)，5: (1，3)，6: (9，4)，7: (8，2)，8: (10，1)}

**方法二:** *使用* [*dict()*](https://www.geeksforgeeks.org/python-dictionary/) *和* [*枚举()*](https://www.geeksforgeeks.org/enumerate-in-python/#:~:text=Enumerate()%20method%20adds%20a,tuples%20using%20list()%20method.)

在本文中，我们使用 dict()将元组列表转换为字典，并使用 enumerate()提供索引。

## 蟒蛇 3

```py
# initializing list
test_list = [(4, 5), (1, 3), (9, 4), (8, 2), (10, 1)]

# printing original list
print("The original list is : " + str(test_list))

# initializing start
start = 4

res = dict(enumerate(test_list, start=start))

# printing result
print("Constructed dictionary : " + str(res))
```

**输出:**

> 原清单为:[(4，5)，(1，3)，(9，4)，(8，2)，(10，1)]
> 
> 构造字典:{4: (4，5)，5: (1，3)，6: (9，4)，7: (8，2)，8: (10，1)}