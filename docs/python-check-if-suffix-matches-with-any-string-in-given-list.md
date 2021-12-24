# Python |检查后缀是否与给定列表中的任何字符串匹配

> 原文:[https://www . geesforgeks . org/python-检查后缀是否与给定列表中的任何字符串匹配/](https://www.geeksforgeeks.org/python-check-if-suffix-matches-with-any-string-in-given-list/)

给定一个字符串列表，任务是检查后缀是否与给定列表中的任何字符串匹配。

**示例:**

```
Input: lst = ["Paras", "Geeksforgeeks", "Game"], str = 'Geeks'
Output:  True

Input: lst = ["Geeks", "for", "forgeeks"], str = 'John'
Output:  False
```

让我们讨论几个完成任务的方法。

**方法#1:使用`any()`**
检查字符串列表中是否存在后缀最简洁易读的方法是使用 any()。

```
# Python code to check whether
# suffix exists in list of strings.

# Input list initialization
lst = ["Paras", "Geeksforgeeks", "Game"]

# using any to find suffix
Output = any('Geek' in x for x in lst)

# Printing output
print("Initial List is :", lst)
print(Output)
```

**Output:**

```
Initial List is : ['Paras', 'Geeksforgeeks', 'Game']
True

```

**方法 2:使用`filter()`和`lambda`**
这是使用 lambda()执行该特定任务的另一种方式。

```
# Python code to check whether
# suffix exists in list of strings.

# Input list initialization
lst = ["Paras", "Geeksforgeeks", "Game"]

# Using filter and lambda
Output = len(list(filter(lambda x: "Jai" in x, lst))) != 0

# Printing output
print("Initial List is :", lst)
print(Output)
```

**Output:**

```
Initial List is : ['Paras', 'Geeksforgeeks', 'Game']
False

```