# Python–字符串中的前 K 个连续数字

> 原文:[https://www . geeksforgeeks . org/python-第一个-k-连续数字字符串/](https://www.geeksforgeeks.org/python-first-k-consecutive-digits-in-string/)

给定一个字符串和数字 K，提取构成数字的前 K 个连续数字。

> **输入**:test _ str = " geeks 5 geeks s43best "，K = 2
> **输出** : 43
> **解释** : 43 是前 2 个连续的数字。
> 
> **输入**:test _ str = " geeks 5 gee 2k 439 best "，K = 3
> **输出** : 439
> **说明** : 439 为前 3 位连续数字。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在这种情况下，我们在列表中运行一个循环，检查当前数字是否存在有效的 N 个连续元素，如果存在，我们返回这 N 个元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# First K consecutive digits in String
# Using loop

# initializing string
test_str = "geeks5geeks43isbest"

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 2

# using loop to run through characters 
res = ""
for idx in range(len(test_str) - K + 1):
        is_num = True

        # check for valid number of consecutives
        for j in range(K):
            is_num = is_num & test_str[idx + j].isdigit()

        # extracting numbers 
        if is_num :
            res = ""
            for j in range(K):
                res += test_str[idx + j]

# printing result 
print("Required character digits : " + str(res)) 
```

**Output**

```
The original string is : geeks5geeks43isbest
Required character digits : 43

```

**方法 2:使用正则表达式()**

这是执行这项任务的另一种方式。在这种情况下，我们应用有效的正则表达式，在处理之后，结果作为出现返回，第一个返回。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# First K consecutive digits in String
# Using regex()
import re

# initializing string
test_str = "geeks5geeks43isbest"

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 2

# using regex() to solve problem
temp = re.search('\d{% s}'% K, test_str)
res = (temp.group(0) if temp else '')

# printing result 
print("Required character digits : " + str(res)) 
```

**Output**

```
The original string is : geeks5geeks43isbest
Required character digits : 43

```