# Python–将字符串转换为字符矩阵

> 原文:[https://www . geesforgeks . org/python-convert-string-to-character-matrix/](https://www.geeksforgeeks.org/python-convert-strings-to-character-matrix/)

有时，在处理字符串列表时，我们会遇到一个问题，需要将列表中的字符串转换为单独的字符列表。整体转换为矩阵。这在我们处理大量数据的数据科学领域有多种应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
这是执行该任务的一种方式。在本例中，我们使用 list()将字符串转换为字符列表，并将结果转换为所需的矩阵。

```py
# Python3 code to demonstrate 
# Convert Strings to Character Matrix
# using List comprehension

# Initializing list
test_list = ['gfg', 'is', 'best']

# printing original list
print("The original list is : " + str(test_list))

# Convert Strings to Character Matrix
# using List comprehension
res = [list(sub) for sub in test_list]

# printing result 
print ("List String after conversion to Matrix : " + str(res))
```

**Output :**

> 原列表为:['gfg '，' is '，' best']
> 转换为 Matrix 后的列表字符串:['g '，' f '，' g']，['i '，' s']，['b '，' e '，' s '，' t']]