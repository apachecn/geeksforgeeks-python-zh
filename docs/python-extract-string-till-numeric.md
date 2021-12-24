# Python–提取字符串直到数字

> 原文:[https://www . geesforgeks . org/python-extract-string-till-numeric/](https://www.geeksforgeeks.org/python-extract-string-till-numeric/)

给定一个字符串，提取它的所有内容，直到第一次出现数字字符。

> **输入**:test _ str = " geeksforgeek 7 最好"
> **输出**:geeksforgeek
> **说明**:7 之前的字符全部提取。
> 
> **输入**:test _ str =“2 geekforgek S7 最好”
> **输出**:
> **解释**:第一个字母提取的字符都不是数字。

**方法#1:使用 isdigit() + index() +循环**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用 isdigit()检查数字的首次出现，并使用 index()获取所需的索引，直到需要提取哪些内容。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract String till Numeric
# Using isdigit() + index() + loop

# initializing string
test_str = "geeks4geeks is best"

# printing original string
print("The original string is : " + str(test_str))

# loop to iterating characters
temp = 0
for chr in test_str:

  # checking if character is numeric,
  # saving index
  if chr.isdigit():
     temp = test_str.index(chr)

# printing result 
print("Extracted String : " + str(test_str[0 : temp])) 
```

**Output**

```
The original string is : geeks4geeks is best
Extracted String : geeks

```

**方法 2:使用正则表达式()**

这是执行这项任务的另一种方式。使用适当的正则表达式()，可以在可能的数字之前获取内容。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract String till Numeric
# Using regex()
import re

# initializing string
test_str = "geeks4geeks is best"

# printing original string
print("The original string is : " + str(test_str))

# regex to get all elements before numerics
res = re.findall('([a-zA-Z ]*)\d*.*', test_str)

# printing result 
print("Extracted String : " + str(res[0])) 
```

**Output**

```
The original string is : geeks4geeks is best
Extracted String : geeks

```