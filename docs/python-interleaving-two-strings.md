# Python |交错两个字符串

> 原文:[https://www . geesforgeks . org/python-交错-双字符串/](https://www.geeksforgeeks.org/python-interleaving-two-strings/)

有时，在处理字符串时，我们有组合两个字符串的任务，即根据效用交错它们。这种实用程序在编写游戏代码时非常有用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`join() + zip()`**
该任务可以使用上述功能执行。在这个连接函数中，执行在索引处连接每个元素对两个字符串的任务，而 zip 执行在每个字符串处交错字符的任务。

```py
# Python3 code to demonstrate
# Interleaving two strings
# using join() + zip()

# initializing strings 
test_string1 = 'geeksforgeeks'
test_string2 = 'computerfreak'

# printing original strings  
print("The original string 1 : " + test_string1)
print("The original string 2 : " + test_string2)

# using join() + zip()
# Interleaving two strings
res = "".join(i + j for i, j in zip(test_string1, test_string2))

# print result
print("The Interleaved string : " + str(res))
```

**Output :**

```py

The original string 1 : geeksforgeeks
The original string 2 : computerfreak
The Interleaved string : gceoemkpsuftoerrgfereekask

```