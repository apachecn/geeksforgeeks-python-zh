# Python |将字符串转换为元组列表

> 原文:[https://www . geesforgeks . org/python-convert-string-to-tuple-list/](https://www.geeksforgeeks.org/python-convert-string-to-tuple-list/)

有时，在使用 Python 字符串时，我们可能会遇到一个问题，即我们收到一个元组，以逗号分隔的字符串格式列出，并且必须转换为元组列表。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `split() + replace()`**
这是一个执行这个任务的蛮力方法。在本文中，我们使用 split()和 replace()功能来执行提取和重新构建元组以在循环中列出的任务。

```
# Python3 code to demonstrate working of
# Convert String to tuple list
# using loop + replace() + split()

# initializing string 
test_str = "(1, 3, 4), (5, 6, 4), (1, 3, 6)"

# printing original string 
print("The original string is : " + test_str)

# Convert String to tuple list
# using loop + replace() + split()
res = []
temp = []
for token in test_str.split(", "):
    num = int(token.replace("(", "").replace(")", ""))
    temp.append(num)
    if ")" in token:
       res.append(tuple(temp))
       temp = []

# printing result
print("List after conversion from string : " + str(res))
```

**Output :**

```
The original string is : (1, 3, 4), (5, 6, 4), (1, 3, 6)
List after conversion from string : [(1, 3, 4), (5, 6, 4), (1, 3, 6)]

```