# Python–检查两个字符串是否旋转等价

> 原文:[https://www . geesforgeks . org/python-检查两个字符串是否旋转等效/](https://www.geeksforgeeks.org/python-check-if-two-strings-are-rotationally-equivalent/)

有时，在使用 Python Strings 时，我们可能会遇到这样的问题:我们需要检查一个字符串是否可以在向左或向右旋转时从其他字符串中派生出来。这类问题可以应用于许多领域，如 web 开发和竞争性编程。让我们讨论执行这项任务的某些方法。

> **输入** : test_str1 = 'GFG '，test _ str 2 = ' FGG '
> T3】输出:真
> 
> **输入** : test_str1 = '极客'，test _ str 2 = ' ksege '
> T3】输出:假

**方法#1:使用循环+字符串切片**
以上功能的组合可以用来解决这个问题。在这种情况下，我们执行提取字符串以执行所有可能的旋转的任务，以检查任何旋转是否等于另一个字符串。

```
# Python3 code to demonstrate working of 
# Check if two strings are Rotationally Equivalent
# Using loop + string slicing

# initializing strings
test_str1 = 'geeks'
test_str2 = 'eksge'

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# Check if two strings are Rotationally Equivalent
# Using loop + string slicing
res = False
for idx in range(len(test_str1)):
        if test_str1[idx: ] + test_str1[ :idx] == test_str2:
            res = True
            break

# printing result 
print("Are two strings Rotationally equal ? : " + str(res)) 
```

**Output :**

```
The original string 1 is : geeks
The original string 2 is : eksge
Are two strings Rotationally equal ? : True

```

**方法 2:使用`any() + join() + enumerate()`**
这是可以执行此任务的方式之一。在本文中，我们使用嵌套生成器表达式提取的 any()和 enumerate()来执行检查任何旋转等价的任务。

```
# Python3 code to demonstrate working of 
# Check if two strings are Rotationally Equivalent
# Using any() + join() + enumerate()

# initializing strings
test_str1 = 'geeks'
test_str2 = 'eksge'

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# Check if two strings are Rotationally Equivalent
# Using any() + join() + enumerate()
res = any(''.join([test_str2[idx2 - idx1] 
        for idx2, val2 in enumerate(test_str2)]) == test_str1
        for idx1, val1 in enumerate(test_str1))

# printing result 
print("Are two strings Rotationally equal ? : " + str(res)) 
```

**Output :**

```
The original string 1 is : geeks
The original string 2 is : eksge
Are two strings Rotationally equal ? : True

```