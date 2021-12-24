# Python |将字符串列表转换为嵌套字符列表

> 原文:[https://www . geesforgeks . org/python-convert-string-list-to-nested-character-list/](https://www.geeksforgeeks.org/python-convert-string-list-to-nested-character-list/)

有时候，在使用 Python 时，我们可能会遇到一个问题，那就是我们需要执行数据的相互转换。在本文中，我们讨论将字符串列表转换为由逗号分隔的嵌套字符列表。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `split()`**
上述功能的组合可用于执行该任务。在本文中，我们使用列表理解来遍历列表，并可以使用 split()来执行拆分。

```py
# Python3 code to demonstrate working of
# Convert String List to Nested Character List
# using split() + list comprehension

# initialize list 
test_list = ["a, b, c", "gfg, is, best", "1, 2, 3"]

# printing original list 
print("The original list : " + str(test_list))

# Convert String List to Nested Character List
# using split() + list comprehension
res = [char.split(', ') for char in test_list]

# printing result
print("List after performing conversion : " + str(res))
```

**Output :**

> 原列表:['a，b，c '，' gfg，is，best '，' 1，2，3']
> 执行转换后的列表:['a '，' b '，' c']，['gfg '，' is '，' best']，['1 '，' 2 '，' 3']]