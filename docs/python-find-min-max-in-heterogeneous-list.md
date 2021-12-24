# Python |在异构列表中查找最小值/最大值

> 原文:[https://www . geesforgeks . org/python-find-min-max-in-异类-list/](https://www.geeksforgeeks.org/python-find-min-max-in-heterogeneous-list/)

Python 中的列表可以处理不同类型的数据类型。这种列表的操作很复杂。假设我们有一个问题，我们需要找到最小/最大整数值，其中列表可以包含字符串作为数据类型，即异类。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+min()/max()+isinstance()**
这个特殊的问题可以通过使用 is instance 方法过滤我们对 min/max 的搜索来解决，我们可以过滤掉整数值，然后可以使用 min/max 函数来获得所需的 min/max 值。

## 蟒蛇 3

```py
# Python3 code to demonstrate 
# Min / Max in heterogeneous list
# using list comprehension + min()/max() + isinstance()

# initializing list
test_list = [3, 'computer', 5, 'geeks', 6, 7]

# printing original list
print ("The original list is : " + str(test_list))

# using list comprehension + min()/max() + isinstance()
# Min / Max in heterogeneous list
res = min(i for i in test_list if isinstance(i, int))

# printing result
print ("The minimum value in list is : " + str(res))
```

**Output : **

```py
The original list is : [3, 'computer', 5, 'geeks', 6, 7]
The minimum value in list is : 3
```

**方法#2:使用 lambda+key+max()/min()+isinstance()**
上面的问题也可以通过使用 lambda 函数作为 min()/max()中的键以及执行检查整数值任务的 is instance 方法来解决。

## 蟒蛇 3

```py
# Python3 code to demonstrate 
# Min / Max in heterogeneous list
# using lambda + key + max()/min() + isinstance()

# initializing list
test_list = [3, 'computer', 5, 'geeks', 6, 7]

# printing original list
print ("The original list is : " + str(test_list))

# using lambda + key + max()/min() + isinstance()
# Min / Max in heterogeneous list
res = max(test_list, key = lambda i: (isinstance(i, int), i))

# printing result
print ("The maximum value in list is : " + str(res))
```

**Output : **

```py
The original list is : [3, 'computer', 5, 'geeks', 6, 7]
The maximum value in list is : 7
```