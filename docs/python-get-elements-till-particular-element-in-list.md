# Python |获取元素直到列表中的特定元素

> 原文:[https://www . geesforgeks . org/python-get-elements-till-special-element-in-list/](https://www.geeksforgeeks.org/python-get-elements-till-particular-element-in-list/)

有时，在使用 Python 列表时，我们可能会有一个要求，即需要移除特定元素之后的所有元素，或者获取特定元素之前的所有元素。这两个都是相似的问题，有一个解决方案总是有帮助的。让我们讨论执行这项任务的某些方法。

**方法#1:使用`index()` +列表切片**
结合这些功能可以解决这个问题。`index()`可用于查找所需元素的索引，列表切片可执行获取元素的剩余任务。

```
# Python3 code to demonstrate working of
# Get elements till particular element in list
# using index() + list slicing

# initialize list
test_list = [1, 4, 6, 8, 9, 10, 7]

# printing original list
print("The original list is : " + str(test_list))

# declaring elements till which elements required
N = 8

# Get elements till particular element in list
# using index() + list slicing
temp = test_list.index(N)
res = test_list[:temp]

# printing result
print("Elements till N in list are : " + str(res))
```

**Output :**

```
The original list is : [1, 4, 6, 8, 9, 10, 7]
Elements till N in list are : [1, 4, 6]

```