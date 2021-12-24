# Python |检查 ASCII 字符串

> 原文:[https://www . geesforgeks . org/python-check-for-ascii-string/](https://www.geeksforgeeks.org/python-check-for-ascii-string/)

很多时候，处理只包含字母的字符串是可取的，而其他特殊字符是不可取的，有时这个任务成为过滤字符串的关键，因此需要检查字符串是否是完整的 ASCII。让我们讨论执行这项任务的某些方法。

**方法#1:使用`ord() + all()`**
这种方法的组合可以用来实现理想的任务。在这个方法中，我们搜索所有的字符串并检查每个字符，一个 ASCII 字符范围内的值。

```
# Python3 code to demonstrate
# Check for ASCII string
# using all() + ord()

# initializing string 
test_string = "G4G is best"

# printing original string 
print("The original string : " + str(test_string))

# using all() + ord()
# Check for ASCII string
res = all(ord(c) < 128 for c in test_string)

# print result
print("Is the string full ASCII ? : " + str(res))
```

**Output :**

```
The original string : G4G is best
Is the string full ASCII ? : True

```