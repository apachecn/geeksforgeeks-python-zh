# Python |将字符串转换为元组列表

> 原文:[https://www . geesforgeks . org/python-convert-string-to-list-of-tuples/](https://www.geeksforgeeks.org/python-convert-string-to-list-of-tuples/)

有时，在处理数据时，我们会遇到一个问题，即我们有一个字符串数据列表，我们需要将其转换为记录列表。这种问题会在我们处理大量字符串数据时出现。让我们讨论执行这项任务的某些方法。

**方法一:使用 `zip() + split() + list slicing`**
以上功能的组合可以用来解决这个问题。在这种情况下，首先将字符串转换为字符串列表，然后使用`zip()`和列表切片功能制作所需的元组。

```
# Python3 code to demonstrate working of
# Convert String to list of tuples
# Using zip() + list slicing + split()

# initialize string 
test_string = "GFG is best Computer Science Portal"

# printing original string 
print("The original string : " + str(test_string))

# Convert String to list of tuples
# Using zip() + list slicing + split()
temp = test_string.split()
res = list(zip(temp[::2], temp[1::2]))

# printing result
print("List after String to tuple conversion : " + str(res))
```

**Output :**

> 原字符串:GFG 最佳计算机科学门户
> 字符串到元组转换后的列表:[('GFG '，' is ')，('最佳'，'计算机'，('科学'，'门户')]