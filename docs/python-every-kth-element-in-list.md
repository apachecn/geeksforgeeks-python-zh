# Python |列表中的每一个 Kth 元素

> 原文:[https://www . geesforgeks . org/python-ever-kth-element-in-list/](https://www.geeksforgeeks.org/python-every-kth-element-in-list/)

有时，在使用 Python 列表时，我们会遇到一个问题，我们需要提取列表的每个 Kth 元素，并从中分割出一个新列表。作为列表切片的一种变体，这种类型的问题非常常见。让我们来讨论一下如何做到这一点。

**方法:使用列表切片**
这个任务可以使用列表切片功能来执行。这里的技巧是使用 list 的跳过功能来获取 list 的每个 Kth 元素。定义的 k 可以用作跳过元素。

```py
# Python3 code to demonstrate working of
# Kth element list
# Using list slicing 

# initializing list
test_list = [6, 4, 8, 9, 10, 5, 8, 9, 10, 2, 34, 5]

# printing list
print("The original list : " + str(test_list))

# initializing K 
K = 3

# Kth element list
# Using list slicing 
res = test_list[::K]

# Printing result
print("Kth element list is : " + str(res))
```

**Output :**

```py

The original list : [6, 4, 8, 9, 10, 5, 8, 9, 10, 2, 34, 5]
Kth element list is : [6, 9, 8, 2]

```