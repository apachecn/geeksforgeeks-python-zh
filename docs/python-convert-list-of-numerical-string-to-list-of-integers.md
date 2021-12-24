# Python |将数字字符串列表转换为整数列表

> 原文:[https://www . geesforgeks . org/python-convert-list-of-numeric-string-to-list-of-integer/](https://www.geeksforgeeks.org/python-convert-list-of-numerical-string-to-list-of-integers/)

很多时候，我们处理的数据可能不是任何应用程序所需的形式，必须经过预处理阶段。一种这样的形式可以是字符串形式的数字，也可以是列表中的列表，我们需要将它分隔为数字分隔的整数。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解**
这个问题可以用列表理解来处理，作为一种通用循环的简写，我们需要通过迭代每个列表的每个字符串并转换成整数来运行该循环来执行这个特定的任务。

```py
# Python3 code to demonstrate
# converting string list to integer list
# using list comprehension

# initializing list
test_list = [['24'], ['45'], ['78'], ['40']]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension
# converting string list to integer list
res = [[int(i) for i in sub] for i in test_list for sub in i]

# print result
print("The list after conversion : " + str(res))
```

**Output :**

```py
The original list : [['24'], ['45'], ['78'], ['40']]
The list after conversion : [[2, 4], [4, 5], [7, 8], [4, 0]]

```