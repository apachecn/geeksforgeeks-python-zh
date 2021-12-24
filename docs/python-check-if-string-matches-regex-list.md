# Python |检查字符串是否匹配正则表达式列表

> 原文:[https://www . geesforgeks . org/python-check-if-string-matches-regex-list/](https://www.geeksforgeeks.org/python-check-if-string-matches-regex-list/)

有时，在使用 Python 时，我们会遇到一个问题，我们有一个正则表达式列表，我们需要检查一个特定的字符串是否与列表中任何可用的正则表达式相匹配。让我们讨论一下执行这项任务的方法。

**方法:使用 join regex + loop + `re.match()`**
该任务可以使用以上功能的组合来执行。在本例中，我们通过连接所有正则表达式列表来创建一个新的正则表达式字符串，然后使用 match()将该字符串与正则表达式列表中的任何元素进行匹配，以检查匹配情况。

```
# Python3 code to demonstrate working of
# Check if string matches regex list
# Using join regex + loop + re.match()
import re

# initializing list 
test_list = ["gee*", "gf*", "df.*", "re"]

# printing list 
print("The original list : " + str(test_list))

# initializing test_str 
test_str = "geeksforgeeks"

# Check if string matches regex list
# Using join regex + loop + re.match()
temp = '(?:% s)' % '|'.join(test_list)
res = False
if re.match(temp, test_str):
    res = True

# Printing result
print("Does string match any of regex in list ? : " + str(res))
```

**Output :**

```

The original list : ['gee*', 'gf*', 'df.*', 're']
Does string match any of regex in list ? : True

```