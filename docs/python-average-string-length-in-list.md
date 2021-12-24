# Python |列表中的平均字符串长度

> 原文:[https://www . geesforgeks . org/python-average-string-in-length-list/](https://www.geeksforgeeks.org/python-average-string-length-in-list/)

有时，在处理数据时，我们会遇到一个问题，需要收集列表中字符串数据的平均长度信息。这种信息可能在数据科学领域有用。让我们讨论执行这项任务的某些方法。

**方法一:使用列表理解+ `sum() + len()`**
以上功能的组合可以用来执行这个任务。在本文中，我们使用列表理解计算所有字符串的长度，然后使用`len() and sum()`将总和除以列表的长度。

```
# Python3 code to demonstrate working of
# Average String lengths in list
# using list comprehension + sum() + len()

# initialize list 
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list 
print("The original list : " + str(test_list))

# Average String lengths in list
# using list comprehension + sum() + len()
temp = [len(ele) for ele in test_list]
res = 0 if len(temp) == 0 else (float(sum(temp)) / len(temp)) 

# printing result
print("The Average length of String in list is : " + str(res))
```

**Output :**

```
The original list : ['gfg', 'is', 'best', 'for', 'geeks']
The Average length of String in list is : 3.4

```