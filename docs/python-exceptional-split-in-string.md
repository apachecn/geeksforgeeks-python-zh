# Python |字符串中的异常拆分

> 原文:[https://www . geesforgeks . org/python-例外-字符串分割/](https://www.geeksforgeeks.org/python-exceptional-split-in-string/)

有时，在使用字符串时，我们可能需要执行拆分操作。直前劈很容易。但是有时候，我们可能会遇到这样的问题，我们需要对某些角色执行拆分，但是有例外。本文讨论逗号的拆分，但逗号不应用括号括起来。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + strip()**
这是我们执行这个任务的蛮力方式。在本例中，我们将列表的每个元素构造为字符串中的单词，并考虑括号和逗号来执行拆分。

```
# Python3 code to demonstrate working of 
# Exceptional Split in String
# Using loop + split()

# initializing string
test_str = "gfg, is, (best, for), geeks"

# printing original string
print("The original string is : " + test_str)

# Exceptional Split in String
# Using loop + split()
temp = ''
res = []
check = 0
for ele in test_str:
    if ele == '(':
        check += 1
    elif ele == ')':
        check -= 1
    if ele == ', ' and check == 0:
        if temp.strip():
            res.append(temp)
        temp = ''
    else:
        temp += ele
if temp.strip():
    res.append(temp)

# printing result 
print("The string after exceptional split : " + str(res)) 
```

**Output :**

```
The original string is : gfg, is, (best, for), geeks
The string after exceptional split : ['gfg', ' is', ' (best, for)', ' geeks']

```