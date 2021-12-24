# Python |检查列表中是否有空字符串

> 原文:[https://www . geesforgeks . org/python-检查列表中是否有空字符串/](https://www.geeksforgeeks.org/python-check-if-any-string-is-empty-in-list/)

有时，在使用 Python 时，我们会遇到一个问题，需要检查列表中数据的完整性。参数之一可以是列表中的每个元素都是非空的。让我们用某些方法来讨论一个列表在这个因素上是否完美。

**方法#1:使用`any() + len()`**
上述功能的组合可用于执行该任务。在本文中，我们使用 any()检查字符串中的任何元素，len()用于获取任何字符串的长度是否为 0。

```py
# Python3 code to demonstrate working of
# Check if any String is empty in list
# using len() + any()

# initialize list 
test_list = ['gfg', 'is', 'best', '', 'for', 'geeks']

# printing original list 
print("The original list : " + str(test_list))

# Check if any String is empty in list
# using len() + any()
res = any(len(ele) == 0 for ele in test_list)

# printing result
print("Is any string empty in list? : " + str(res))
```

**Output :**

```py
The original list : ['gfg', 'is', 'best', '', 'for', 'geeks']
Is any string empty in list? : True

```