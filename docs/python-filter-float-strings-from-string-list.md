# Python–从字符串列表中过滤浮动字符串

> 原文:[https://www . geesforgeks . org/python-filter-float-string-from-string-list/](https://www.geeksforgeeks.org/python-filter-float-strings-from-string-list/)

有时，在使用 Python 列表时，我们会遇到一个问题，需要将浮点值与有效字符串分开。但是当浮点值是字符串形式时，问题就出现了。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+异常处理**
上述功能的组合可用于执行该任务。在这种情况下，我们循环遍历每个元素，并尝试将每个字符串转换为浮点值，如果成功，意味着它是浮点，否则它会引发 ValueError，我们可以获得所需的字符串。

```
# Python3 code to demonstrate working of
# Filter float strings from String list
# using loop + Exception Handling

# initialize list 
test_list = ['gfg', '45.45', 'is', '87.5', 'best', '90.34']

# printing original list 
print("The original list : " + str(test_list))

# Filter float strings from String list
# using loop + Exception Handling
res = []
for ele in test_list:
    try:
        float(ele)
    except ValueError:
        res.append(ele)

# printing result
print("String list after filtering floats : " + str(res))
```

**Output :**

```
The original list : ['gfg', '45.45', 'is', '87.5', 'best', '90.34']
String list after filtering floats : ['gfg', 'is', 'best']

```