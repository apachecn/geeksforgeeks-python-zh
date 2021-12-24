# Python–检查元素是否由 K

分隔

> 原文:[https://www . geesforgeks . org/python-check-if-elements-由-k 分隔/](https://www.geeksforgeeks.org/python-check-if-elements-delimited-by-k/)

给定一个字符串，检查每个段是否由 k 分隔

> **输入** : test_str = '72！45!极客！最佳'，K = '！'
> **输出**:真
> **说明**:所有数字和字母用 delim 边框隔开。
> 
> **输入** : test_str = '72！45 个极客！最佳'，K = '！'
> **输出**:假
> **说明**:45 和极客不分。

**方法:使用 isdigit() + isalpha() +循环**

这是执行这项任务的方法。在本文中，我们使用 isalpha()和 isdigit()执行检查字母和数字段的任务。任何元素(不完全是数字或字母)的存在都被称为非 K 定界，并且在拆分()过程中仍未解决。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Check if Elements delimited by K
# Using isdigit() + isalpha() + loop

# initializing string
test_str = '72@45@geeks@best'

# printing original string
print("The original string is : " + str(test_str))

# initializing splt_chr 
K = "@"

res = True

# splitting elements
temp = test_str.split(K) 

for ele in temp:

    # checking for non-alpha or non-digit
    if len(ele) > 1 and not ele.isdigit() and not ele.isalpha():
        res = False
        break

# printing result 
print("Are all delimited by K : " + str(res)) 
```

**Output**

```py
The original string is : 72@45@geeks@best
Are all delimited by K : True

```