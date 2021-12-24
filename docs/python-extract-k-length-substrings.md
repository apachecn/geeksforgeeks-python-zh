# Python–提取 K 长度子字符串

> 原文:[https://www . geesforgeks . org/python-extract-k-length-substrings/](https://www.geeksforgeeks.org/python-extract-k-length-substrings/)

有很多问题，我们需要得到一个字符串的所有 K 长度子串。这个特殊的实用程序在竞争性编程中非常流行，用人手解决这个问题总是很方便。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解+字符串切片**
列表理解和字符串切片的结合可以用来执行这个特定的任务。这只是执行这个任务的蛮力方法。

```
# Python3 code to demonstrate working of
# Extract K length substrings
# Using list comprehension + string slicing

# initializing string 
test_str = "Geeks"

# printing original string 
print("The original string is : " + str(test_str))

# initializing K 
K = 3

# Extract K length substrings
# Using list comprehension + string slicing
res = [test_str[i: j] for i in range(len(test_str)) for j in range(i + 1, len(test_str) + 1) if len(test_str[i:j]) == K]

# printing result 
print("All K length substrings of string are : " + str(res))
```

**Output :**

```
The original string is : Geeks
All K length substrings of string are : ['Gee', 'eek', 'eks']

```