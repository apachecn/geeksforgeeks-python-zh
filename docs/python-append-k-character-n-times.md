# Python |追加 K 字符 N 次

> 原文:[https://www . geesforgeks . org/python-append-k-character-n-times/](https://www.geeksforgeeks.org/python-append-k-character-n-times/)

有时，我们希望以这样一种方式操作一个字符串，在填充缺失的位或任何其他特定需求的情况下，我们可能需要在字符串的末尾添加额外的 K。这类问题的解决方法总是很方便，如果你有这方面的知识就很好。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`ljust()`**
这个任务可以使用 ljust 的简单内置字符串函数来执行，在这个函数中，我们只需要将所需的 N 次和元素传递到右边的 pad，在这个例子中是 k

```
# Python3 code to demonstrate
# Append K character N times
# using ljust()

# initializing string 
test_string = 'GFG'

# printing original string 
print("The original string : " + str(test_string))

# initializing K 
K = 'M'

# No. of K required
N = 5

# using ljust()
# Append K character N times
res = test_string.ljust(N + len(test_string), K)

# print result
print("The string after adding trailing K : " + str(res))
```

**Output :**

```
The original string : GFG
The string after adding trailing K : GFGMMMMM

```