# Python |自定义连续字符配对

> 原文:[https://www . geesforgeks . org/python-自定义-连续-字符-配对/](https://www.geeksforgeeks.org/python-custom-consecutive-character-pairing/)

有时，在使用 Python Strings 时，我们可能会遇到这样的问题，即需要使用 deliminator 执行连续字符串的配对。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法一:使用`join()` +列表理解**
以上功能的组合可以用来执行此任务。在本文中，我们使用 join()执行连接字符的任务，并使用列表理解执行编译。

```
# Python3 code to demonstrate working of 
# Custom Consecutive Character Pairing
# Using join() + list comprehension
import string

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + test_str)

# initializing Delim
delim = '_'

# Custom Consecutive Character Pairing
# Using join() + list comprehension
res = [delim.join(test_str[idx : idx + 2]) for idx in range(len(test_str) - 1)]

# printing result 
print("The List of joined Characters : " + str(res)) 
```

**Output :**

```
The original string is : geeksforgeeks
The List of joined Characters : ['g_e', 'e_e', 'e_k', 'k_s', 's_f', 'f_o', 'o_r', 'r_g', 'g_e', 'e_e', 'e_k', 'k_s']

```