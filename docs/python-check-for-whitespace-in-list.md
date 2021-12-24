# Python |检查列表中的空白

> 原文:[https://www . geesforgeks . org/python-检查列表中的空白/](https://www.geeksforgeeks.org/python-check-for-whitespace-in-list/)

有时，我们可能会遇到一个问题，我们需要检查字符串列表是否有任何空格。这类问题可以在机器学习领域得到特定类型的数据集。让我们讨论一下解决这类问题的某些方法。

**方法#1:使用正则表达式+ any()**
这种问题可以使用 python 提供的正则表达式实用程序来解决。通过在 search()中输入适当的正则表达式字符串，我们可以检查字符串中是否存在空格，并使用 any()遍历整个列表。

```
# Python3 code to demonstrate working of
# Check for Whitespace in List
# Using regex and any()
import re

# initializing list 
test_list = ["Geeks forGeeks", "is", "best"]

# printing original list
print("The original list is : " + str(test_list))

# Check for Whitespace in List
# Using regex and any()
res = any(bool(re.search(r"\s", ele)) for ele in test_list)

# printing result 
print("Does any string contain spaces ? " + str(res))
```

**Output :**

```
The original list is : ['Geeks forGeeks', 'is', 'best']
Does any string contain spaces ? True

```