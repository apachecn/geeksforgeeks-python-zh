# Python |在前面追加，从后面移除

> 原文:[https://www . geesforgeks . org/python-前追加后移除/](https://www.geeksforgeeks.org/python-append-at-front-and-remove-from-rear/)

熟悉队列的概念，它遵循先进先出规则，即先进先出，这意味着前移后插。这个已经讨论过很多次了。但有时我们需要执行与此完全相反的操作，我们需要在前面执行追加，在后面移除元素。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`+ operator`和列表切片**
这些操作符可以用来执行这个特定的任务。追加操作可以在+运算符的帮助下完成，后置的移除可以使用传统的列表切片来完成。

```py
# Python3 code to demonstrate
# append from front and remove from rear
# using + operator and list slicing

# initializing list
test_list = [4, 5, 7, 3, 10]

# printing original list 
print("The original list : " + str(test_list))

# using + operator and list slicing
# append from front and remove from rear
res = [13] + test_list[:-1]

# printing result
print("The list after append and removal : " + str(res))
```

**Output :**

```py
The original list : [4, 5, 7, 3, 10]
The list after append and removal : [13, 4, 5, 7, 3]

```