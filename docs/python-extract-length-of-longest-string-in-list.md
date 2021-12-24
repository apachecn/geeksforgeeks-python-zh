# Python |提取列表中最长字符串的长度

> 原文:[https://www . geesforgeks . org/python-提取列表中最长字符串的长度/](https://www.geeksforgeeks.org/python-extract-length-of-longest-string-in-list/)

有时，在处理大量数据时，我们会遇到一个问题，需要提取列表中所有字符串的最大长度。这种问题在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`max()` +生成器表达式**
上述功能的组合可用于执行该任务。在本文中，我们使用生成器表达式提取所有列表长度，并使用 max()返回它们的最大值。

```
# Python3 code to demonstrate working of
# Extracting length of longest string in list
# using max() + generator expression

# initialize list 
test_list = ['gfg', 'is', 'best']

# printing original list 
print("The original list : " + str(test_list))

# Extracting length of longest string in list
# using max() + generator expression
res = max(len(ele) for ele in test_list)

# printing result
print("Length of maximum string is : " + str(res))
```

**Output :**

```
The original list : ['gfg', 'is', 'best']
Length of maximum string is : 4

```