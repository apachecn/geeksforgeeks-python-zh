# Python |获取元组列表中第一个最大值的元素

> 原文:[https://www . geesforgeks . org/python-获取元组列表中具有最大值的第一个元素/](https://www.geeksforgeeks.org/python-get-first-element-with-maximum-value-in-list-of-tuples/)

在 Python 中，我们可以以元组的形式绑定结构信息，然后可以检索相同的信息。但有时我们需要对应于其他元组索引最大值的元组信息。这个功能有很多应用，比如排名。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`max() + operator.itemgetter()`**
我们可以使用提供的 key itemgetter 索引从一个列表中获取对应元组索引的最大值，然后在最后使用 index 规范提到需要的索引信息。

```py
# Python3 code to demonstrate 
# to get tuple info. of maximum value tuple
# using max() + itemgetter()
from operator import itemgetter

# initializing list 
test_list = [('Rash', 143), ('Manjeet', 200), ('Varsha', 100)]

# printing original list 
print ("Original list : " + str(test_list))

# using max() + itemgetter()
# to get tuple info. of maximum value tuple
res = max(test_list, key = itemgetter(1))[0]

# printing result
print ("The name with maximum score is : " + res)
```

**Output:**

```py
Original list : [('Rash', 143), ('Manjeet', 200), ('Varsha', 100)]
The name with maximum score is : Manjeet

```