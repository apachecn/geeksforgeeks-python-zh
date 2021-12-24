# Python |将字符矩阵转换为单个字符串

> 原文:[https://www . geesforgeks . org/python-convert-character-matrix-to-single-string/](https://www.geeksforgeeks.org/python-convert-character-matrix-to-single-string/)

有时，在使用 Python 字符串时，我们可以选择执行将字符矩阵转换为单个字符串的任务。这可以在我们需要处理数据的领域中得到应用。让我们讨论一下执行这项任务的某些方法。

**方法#1:使用`join()` +列表理解**
上述功能的组合可用于执行该任务。在这种情况下，我们只需迭代所有列表，并使用 join()连接它们。

```py
# Python3 code to demonstrate working of 
# Convert Character Matrix to single String
# Using join() + list comprehension

# initializing list
test_list = [['g', 'f', 'g'], ['i', 's'], ['b', 'e', 's', 't']]

# printing original list
print("The original list is : " + str(test_list))

# Convert Character Matrix to single String
# Using join() + list comprehension
res = ''.join(ele for sub in test_list for ele in sub)

# printing result 
print("The String after join : " + res) 
```

**Output :**

```py
The original list is : [['g', 'f', 'g'], ['i', 's'], ['b', 'e', 's', 't']]
The String after join : gfgisbest

```