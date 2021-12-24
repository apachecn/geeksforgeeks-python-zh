# Python–连续字母出现

> 原文:[https://www . geeksforgeeks . org/python-连续-字母-出现/](https://www.geeksforgeeks.org/python-consecutive-alphabetic-occurrence/)

有时，在处理字符串时，我们可能会遇到一个问题，即我们需要检查是否可以根据英文字母连续找到字符的出现。这种问题可能发生在学校编程和日常编程中。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `ascii_letters + zip()`**
以上方法的组合可以用来执行这个任务。在本文中，我们使用 ascii_letters 提取英文字母，并使用 zip()检查连续性。

```py
# Python3 code to demonstrate working of 
# Consecutive Alphabetic Occurrence
# Using loop + ascii_letters + zip()
from string import ascii_letters

# initializing string
test_str = 'geeksforgeeks is best fgr geeks'

# printing original string
print("The original string is : " + str(test_str))

# Consecutive Alphabetic Occurrence
# Using loop + ascii_letters + zip()
res = []
for i, j in zip(ascii_letters, ascii_letters[1:]) :
    if i + j in test_str:
        res.append((i, j))

# printing result 
print("The Consecutive matching letter pairs : " + str(res)) 
```

**Output :**

> 原来的字符串是:geeksforgeeks 最好是 fgr geeks
> 连续匹配的字母对:[('f '，' g ')，(' s '，' t')]