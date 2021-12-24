# Python |将字符串列表转换为 ascii 值

> 原文:[https://www . geesforgeks . org/python-convert-string-list-to-ascii-values/](https://www.geeksforgeeks.org/python-convert-string-list-to-ascii-values/)

有时，在使用 Python 时，我们可能会遇到一个问题，需要将字符串列表转换为 ascii 值。这种问题会发生很多次。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `ord()`**
使用上述功能可以解决这个问题。在本例中，我们迭代列表，并使用`ord()`将每个字符转换为其 ascii 数字。

```py
# Python3 code to demonstrate working of
# Convert String list to ascii values
# using loop + ord()

# initialize list 
test_list = ['gfg', 'is', 'best']

# printing original list 
print("The original list : " + str(test_list))

# Convert String list to ascii values
# using loop + ord()
res = []
for ele in test_list:
    res.extend(ord(num) for num in ele)

# printing result
print("The ascii list is : " + str(res))
```

**Output :**

```py
The original list : ['gfg', 'is', 'best']
The ascii list is : [103, 102, 103, 105, 115, 98, 101, 115, 116]

```