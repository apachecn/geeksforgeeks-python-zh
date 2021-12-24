# Python |字符串的前导和尾部填充列表

> 原文:[https://www . geeksforgeeks . org/python-字符串填充列表/](https://www.geeksforgeeks.org/python-lead-and-trail-padding-of-strings-list/)

有时，在处理字符串列表时，我们会遇到一个问题，即需要用特定的字符串填充列表中的每个字符串。这种类型的问题可能出现在 web 开发领域的许多地方。让我们讨论执行这项任务的某些方法。

**方法一:使用列表理解**

这个任务可以通过理解列表来完成。在这种情况下，我们迭代每个字符串元素，并在每个字符串的后面和前面添加所需的字符串后重建一个新的字符串列表。

```
# Python3 code to demonstrate working of
# Trail and lead padding of strings list
# using list comprehension

# initialize list 
test_list = ["a", "b", "c"]

# printing original list 
print("The original list : " + str(test_list))

# initialize pad_str
pad_str = 'gfg'

# Trail and lead padding of strings list
# using list comprehension
res = [pad_str + ele + pad_str  for ele in test_list]

# printing result
print("The String list after padding : " + str(res))
```

**Output :**

```
The original list : ['a', 'b', 'c']
The String list after padding : ['gfgagfg', 'gfgbgfg', 'gfgcgfg']

```

**方法 2:使用列表理解+字符串格式化**

该任务也可以使用上述功能的组合来执行。在本文中，我们使用带格式的字符串 than +运算符来执行填充任务。

```
# Python3 code to demonstrate working of
# Trail and lead padding of strings list
# using list comprehension + string formatting

# initialize list 
test_list = ["a", "b", "c"]

# printing original list 
print("The original list : " + str(test_list))

# initialize pad_str
pad_str = 'gfg'

# Trail and lead padding of strings list
# using list comprehension + string formatting
temp = pad_str + '{0}' + pad_str
res =  [temp.format(ele) for ele in test_list]

# printing result
print("The String list after padding : " + str(res))
```

**Output :**

```
The original list : ['a', 'b', 'c']
The String list after padding : ['gfgagfg', 'gfgbgfg', 'gfgcgfg']

```