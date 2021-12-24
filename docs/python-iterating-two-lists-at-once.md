# Python |一次迭代两个列表

> 原文:[https://www . geesforgeks . org/python-迭代器-一次两个列表/](https://www.geeksforgeeks.org/python-iterating-two-lists-at-once/)

有时候，在使用 Python 列表时，我们会遇到一个问题，那就是我们必须迭代两个列表元素。一个接一个地迭代是一种选择，但是它更麻烦，并且总是建议在此基础上使用一二线性。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop+“+”运算符**
以上功能的组合可以让我们的任务变得更简单。但是这里的缺点是我们可能不得不连接列表，因此会消耗比期望更多的内存。

```py
# Python3 code to demonstrate working of
# Iterating two lists at once
# using loop + "+" operator

# initializing lists
test_list1 = [4, 5, 3, 6, 2]
test_list2 = [7, 9, 10, 0]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Iterating two lists at once
# using loop + "+" operator
# printing result 
print("The paired list contents are : ")
for ele in test_list1 + test_list2:
    print(ele, end =" ")
```

**Output :**

```py
The original list 1 is : [4, 5, 3, 6, 2]
The original list 2 is : [7, 9, 10, 0]
The paired list contents are : 
4 5 3 6 2 7 9 10 0 

```