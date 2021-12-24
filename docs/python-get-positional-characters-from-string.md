# Python |从字符串中获取位置字符

> 原文:[https://www . geesforgeks . org/python-get-positional-characters-from-string/](https://www.geeksforgeeks.org/python-get-positional-characters-from-string/)

有时，在使用 Python 字符串时，我们会遇到一个问题，即需要通过连接字符串中的特定索引元素来创建子字符串。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方法。在这种情况下，我们在索引列表上运行一个循环，并从字符串中连接相应的索引字符。

```
# Python3 code to demonstrate working of
# Get positional characters from String
# using loop

# initializing string 
test_str = "gfgisbest"

# printing original string 
print("The original string is : " + test_str)

# initializing index list 
indx_list = [1, 3, 4, 5, 7]

# Get positional characters from String
# using loop
res = ''
for ele in indx_list:
    res = res + test_str[ele]

# printing result
print("Substring of selective characters : " + res)
```

**Output :**

```
The original string is : gfgisbest
Substring of selective characters : fisbs

```