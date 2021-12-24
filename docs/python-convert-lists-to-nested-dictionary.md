# Python–将列表转换为嵌套字典

> 原文:[https://www . geesforgeks . org/python-convert-list-to-nested-dictionary/](https://www.geeksforgeeks.org/python-convert-lists-to-nested-dictionary/)

有时候，在使用 Python 字典时，我们会遇到一个问题，我们需要将列表转换为嵌套，即每个列表值代表一个新的嵌套级别。这种问题可以应用于包括 web 开发在内的许多领域。让我们讨论执行这项任务的特定方式。

**方法:使用`zip()` +列表理解**
以上功能的组合可以组合执行此任务。在本文中，我们迭代压缩列表，并使用列表理解来呈现嵌套字典。

```py
# Python3 code to demonstrate working of 
# Convert Lists to Nestings Dictionary
# Using list comprehension + zip()

# initializing list
test_list1 = ["gfg", 'is', 'best']
test_list2 = ['ratings', 'price', 'score']
test_list3 = [5, 6, 7]

# printing original list
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))
print("The original list 3 is : " + str(test_list3))

# Convert Lists to Nestings Dictionary
# Using list comprehension + zip()
res = [{a: {b: c}} for (a, b, c) in zip(test_list1, test_list2, test_list3)]

# printing result 
print("The constructed dictionary : " + str(res)) 
```

**Output :**

```py
The original list 1 is : ['gfg', 'is', 'best']
The original list 2 is : ['ratings', 'price', 'score']
The original list 3 is : [5, 6, 7]
The constructed dictionary : [{'gfg': {'ratings': 5}}, {'is': {'price': 6}}, {'best': {'score': 7}}]

```