# Python | K 字符上的组列表

> 原文:[https://www . geesforgeks . org/python-group-list-on-k-character/](https://www.geeksforgeeks.org/python-group-list-on-k-character/)

有时，我们可能会遇到这样一个问题，我们需要根据作为退市者发送的 K 字符将一个列表拆分为多个列表。这种问题可以用于发送消息，也可以用于需要本地列表的列表的情况。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`index()` 和列表切片**
列表切片可用于从本地列表中获取子列表，索引函数可用于检查可能充当分隔符的 K 字符。这样做的缺点是，它只适用于单个拆分，即只能将一个列表拆分为两个子列表。

```
# Python3 code to demonstrate
# Group List on K character
# using index() + list slicing 

# initializing list 
test_list = ['Geeks', 'for', 'M', 'Geeks', 1, 2]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 'M'

# using index() + list slicing
# Group List on K character
temp_idx = test_list.index(K)
res = [test_list[: temp_idx], test_list[temp_idx + 1: ]]

# print result
print("The list of sublist after separation : " + str(res))
```

**Output :**

```
The original list : ['Geeks', 'for', 'M', 'Geeks', 1, 2]
The list of sublist after separation : [['Geeks', 'for'], ['Geeks', 1, 2]]

```