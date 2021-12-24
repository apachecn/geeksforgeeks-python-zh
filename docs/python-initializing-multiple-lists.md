# Python |初始化多个列表

> 原文:[https://www . geesforgeks . org/python-initiating-multi-list/](https://www.geeksforgeeks.org/python-initializing-multiple-lists/)

在实际应用程序中，我们经常不得不处理多个列表，用空列表初始化它们会妨碍代码的可读性。因此，简单地说，需要一个单行代码来执行这项任务，以便清楚地了解声明要使用的列表的类型和数量。

**方法#1:使用*运算符**
我们可以将所有需要的列表用逗号分隔，然后用一个空列表初始化它们，并使用*运算符将该空列表乘以指定的列表数。

```py
# Python3 code to demonstrate 
# to initialize multiple lists
# using * operator

# using * operator
# to initialize multiple lists
list1, list2, list3, list4 = ([], ) * 4

# printing lists
print ("The initialized lists are : ")
print ("List 1 : " + str(list1))
print ("List 2 : " + str(list2))
print ("List 3 : " + str(list3))
print ("List 4 : " + str(list4))
```

**Output:**

```py
The initialized lists are : 
List 1 : []
List 2 : []
List 3 : []
List 4 : []

```