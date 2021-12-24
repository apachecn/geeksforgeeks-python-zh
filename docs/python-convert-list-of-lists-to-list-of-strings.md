# Python |将列表列表转换为字符串列表

> 原文:[https://www . geesforgeks . org/python-convert-list-list-to-list-strings/](https://www.geeksforgeeks.org/python-convert-list-of-lists-to-list-of-strings/)

数据的相互转换现在非常流行，并且有许多应用。在这种情况下，我们可能会遇到一个问题，我们需要将列表列表，即矩阵转换为字符串列表。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `join()`**
上述功能的组合可用于执行该任务。在本例中，我们使用列表理解执行迭代任务，join()用于执行将字符串连接到字符串列表的任务。

```py
# Python3 code to demonstrate working of
# Convert List of lists to list of Strings
# using list comprehension + join()

# initialize list 
test_list = [["g", "f", "g"], ["i", "s"], ["b", "e", "s", "t"]]

# printing original list 
print("The original list : " + str(test_list))

# Convert List of lists to list of Strings
# using list comprehension + join()
res = [''.join(ele) for ele in test_list]

# printing result
print("The String of list is : " + str(res))
```

**Output :**

```py
The original list : [['g', 'f', 'g'], ['i', 's'], ['b', 'e', 's', 't']]
The String of list is : ['gfg', 'is', 'best']

```