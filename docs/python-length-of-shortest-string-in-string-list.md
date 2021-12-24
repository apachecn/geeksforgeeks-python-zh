# Python–字符串列表中最短字符串的长度

> 原文:[https://www . geesforgeks . org/python-字符串列表中的最短字符串长度/](https://www.geeksforgeeks.org/python-length-of-shortest-string-in-string-list/)

有时，在处理大量数据时，我们会遇到一个问题，需要提取列表中所有字符串的最小长度字符串。这种问题在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用 `min()` +生成器表达式**
上述功能的组合可用于执行该任务。在本文中，我们使用生成器表达式提取所有列表长度，并使用 min()返回它们的最小值。

```py
# Python3 code to demonstrate working of
# Minimum String length
# using min() + generator expression

# initialize list 
test_list = ['gfg', 'is', 'best']

# printing original list 
print("The original list : " + str(test_list))

# Minimum String length
# using min() + generator expression
res = min(len(ele) for ele in test_list)

# printing result
print("Length of minimum string is : " + str(res))
```

**Output :**

```py
The original list : ['gfg', 'is', 'best']
Length of minimum string is : 2

```