# Python |提取除 K 字符串之外的字符

> 原文:[https://www . geesforgeks . org/python-extract-characters-of-k-string/](https://www.geeksforgeeks.org/python-extract-characters-except-of-k-string/)

有时，在使用 Python 字符串时，我们会遇到一个问题，即我们需要提取字符串的所有元素，除了子字符串中的元素。这是一个很常见的问题，在很多领域都有应用，包括日常编程和竞争性编程。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是解决这个问题的蛮力方法。在这种情况下，我们使用 not 运算符来测试主字符串中的元素是否存在，如果元素不存在于 K 字符串中，则提取它。

```py
# Python3 code to demonstrate working of 
# Extract characters except of K string
# Using loop

# initializing strings
test_str1 = "geeksforgeeks is best"
test_str2 = "fes"

# printing original strings
print("The original string 1 is : " + test_str1)
print("The original string 2 is : " + test_str2)

# Extract characters except of K string
# Using loop
res = []
for ele in test_str1:
    if ele not in test_str2:
        res.append(ele)
res = ''.join(res)

# printing result 
print("String after removal of substring elements : " + str(res)) 
```

**Output :**

```py
The original string 1 is : geeksforgeeks is best
The original string 2 is : fes
String after removal of substring elements : gkorgk i bt

```