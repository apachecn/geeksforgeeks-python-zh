# Python–将键值字符串转换为字典

> 原文:[https://www . geesforgeks . org/python-convert-key-value-string-to-dictionary/](https://www.geeksforgeeks.org/python-convert-key-value-string-to-dictionary/)

有时，在使用 Python 字符串时，我们可能会遇到需要将字符串键值对转换为字典的问题。这可能会有我们处理字符串数据并需要转换的应用程序。让我们讨论执行这项任务的某些方法。

**方法#1:使用`map() + split()` +循环**
上述功能的组合可用于执行该任务。在本文中，我们使用 map 执行键值对到字典的转换，并使用 split()完成键值对的拆分。

```py
# Python3 code to demonstrate working of 
# Convert key-value String to dictionary
# Using map() + split() + loop

# initializing string
test_str = 'gfg:1, is:2, best:3'

# printing original string
print("The original string is : " + str(test_str))

# Convert key-value String to dictionary
# Using map() + split() + loop
res = []
for sub in test_str.split(', '):
    if ':' in sub:
        res.append(map(str.strip, sub.split(':', 1)))
res = dict(res)

# printing result 
print("The converted dictionary is : " + str(res)) 
```

**Output :**

```py
The original string is : gfg:1, is:2, best:3
The converted dictionary is : {'gfg': '1', 'is': '2', 'best': '3'}

```