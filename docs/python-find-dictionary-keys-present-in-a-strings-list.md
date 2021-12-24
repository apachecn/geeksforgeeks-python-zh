# Python–查找字符串列表中的字典键

> 原文:[https://www . geesforgeks . org/python-find-dictionary-key-present-in-a-strings-list/](https://www.geeksforgeeks.org/python-find-dictionary-keys-present-in-a-strings-list/)

有时，在使用 Python 字典时，我们可能会遇到这样的问题，即需要从馈送的字符串列表中提取字典键。这个问题可以应用于包括数据在内的许多领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
这是一种蛮力方式，可以执行这个任务。在这种情况下，我们使用条件语句来查找每个字符串中匹配关键字的字符串，并从字符串列表中提取关键字。

```py
# Python3 code to demonstrate working of 
# Extract dictionary keys in Strings List
# Using list comprehension

# initializing list
test_list = ["GeeksforGeeks is best for geeks", "I love GeeksforGeeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing dictionary
test_dict = {'Geeks' : 5, 'CS' : 6, 'best' : 7, 'love' : 10}

# Extract dictionary keys in Strings List
# Using list comprehension
res = [ele if len(ele) > 0 else [None] for ele in [[key for key in test_dict if key in sub]
                                       for sub in test_list]]

# printing result 
print("The matching keys list : " + str(res)) 
```

**Output :**

```py
The original list is : ['GeeksforGeeks is best for geeks', 'I love GeeksforGeeks']
The matching keys list : [['best', 'Geeks'], ['love', 'Geeks']]

```