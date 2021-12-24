# Python |将字符串元组转换为列表元组

> 原文:[https://www . geesforgeks . org/python-convert-string-元组-to-list-元组/](https://www.geeksforgeeks.org/python-convert-string-tuples-to-list-tuples/)

有时，在使用 Python 时，我们会遇到一个问题，即我们有一个字符串形式的元组形式的记录列表，我们希望将它们转换为元组列表。这种问题在数据科学领域会有它的出现。让我们讨论执行这项任务的某些方法。

**方法一:使用`eval()` +列表理解**
利用`eval()`的内置功能，这个问题可以很容易地作为一个线性来执行，它执行字符串到元组转换和列表理解的任务。

```
# Python3 code to demonstrate working of
# Converting string tuples to list tuples 
# using list comprehension + eval()

# Initializing list 
test_list = ["('gfg', 1)", "('is', 2)", "('best', 3)"]

# printing original list 
print("The original list is : " + str(test_list))

# Converting string tuples to list tuples 
# using list comprehension + eval()
res = [eval(ele) for ele in test_list]

# printing result
print("The list tuple after conversion : " + str(res))
```

**Output :**

```
The original list is : ["('gfg', 1)", "('is', 2)", "('best', 3)"]
The list tuple after conversion : [('gfg', 1), ('is', 2), ('best', 3)]

```