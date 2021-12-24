# Python–不区分大小写的字符串计数器

> 原文:[https://www . geesforgeks . org/python-不区分大小写-字符串-计数器/](https://www.geeksforgeeks.org/python-case-insensitive-string-counter/)

给定字符串列表，查找不区分大小写的字符串频率。

> **输入**:test _ list =[“Gfg”、“Best”、“Gfg”、“is”、“Best”]
> **输出**:{‘Gfg’:2、‘Best’:2、‘IS’:2 }
> **解释**:均出现两次。
> 
> **输入**:test _ list =[“Gfg”、“Gfg”、“GFG”]
> **输出**:{“Gfg”:3 }
> **说明**:仅“Gfg”3 次出现。

**方法:使用 defaultdict() + lower()**

在这种情况下，我们对所有字符串执行 lower()，然后在 defaultdict 中映射。这确保了映射和累积频率时不区分大小写。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Strings Frequency (Case Insensitive)
# Using defaultdict() + lower()
from collections import defaultdict

# initializing list
test_list = ["Gfg", "Best", "best", "gfg", "GFG", "is", "IS", "BEST"]

# printing original list
print("The original list is : " + str(test_list))

res = defaultdict(int)
for ele in test_list:

    # lowercasing to cater for Case Insensitivity
    res[ele.lower()] += 1

# printing result 
print("Strings Frequency : " + str(dict(res)))
```

**Output**

```py
The original list is : ['Gfg', 'Best', 'best', 'gfg', 'GFG', 'is', 'IS', 'BEST']
Strings Frequency : {'gfg': 3, 'best': 3, 'is': 2}

```