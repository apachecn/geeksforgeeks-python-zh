# Python–使用自定义值列表初始化字典

> 原文:[https://www . geesforgeks . org/python-initialize-dictionary-with-custom-value-list/](https://www.geeksforgeeks.org/python-initialize-dictionary-with-custom-value-list/)

在 python 中，人们通常会遇到必须使用字典来存储列表的情况。但是在这些情况下，人们通常会检查第一个元素，然后在它出现时创建一个对应于 key 的列表。但是它一直想要一个初始化字典的方法。带有自定义列表的键。让我们讨论实现这个特殊任务的某些方法。

**方法#1:使用字典理解**
这是最受欢迎的初始化方法。在这种方法中，我们创建所需的键数，然后在继续创建键的同时初始化 customlist，以便于之后的追加操作而不会出错。

```
# Python3 code to demonstrate 
# Custom list dictionary initialization
# using dictionary comprehension

# initialize custom list 
cus_list = [4, 6]

# using dictionary comprehension to construct
new_dict = {new_list: cus_list for new_list in range(4)}

# printing result
print ("New dictionary with custom list as keys : " + str(new_dict))
```

**Output :**

```
New dictionary with custom list as keys : {0: [4, 6], 1: [4, 6], 2: [4, 6], 3: [4, 6]}

```