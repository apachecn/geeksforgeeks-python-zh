# python \ get 将哪个元素转换为

> 原文:[https://www . geesforgeks . org/python-get-kth-element-till-n/](https://www.geeksforgeeks.org/python-get-kth-element-till-n/)

有时，我们可能会遇到一个实用程序，其中我们需要获取前 N 个子列表元素，这些元素也只有一个特定的索引。这可以让一个应用程序在排队时只得到第 N 个人的名字。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解和列表切片**
上面两个强大的 Python 实用程序在这里也可以得到结果，因为列表理解可以提取元素切片可以限制我们需要提取的大小。

```py
# Python3 code to demonstrate
# Get Kth element till N
# using list comprehension + list slicing 

# initializing list 
test_list = [['Geeks', 1, 15], ['for', 3, 5], ['Geeks', 3, 7]]

# printing original list 
print("The original list : " + str(test_list))

# initializing N
N = 2

# initializing K 
K = 1

# using list comprehension + list slicing
# Get Kth element till N
res = [i[K] for i in test_list[ : N]] 

# print result
print("The Kth element of sublist till N : " + str(res))
```

**Output :**

```py
The original list : [['Geeks', 1, 15], ['for', 3, 5], ['Geeks', 3, 7]]
The Kth element of sublist till N : [1, 3]

```