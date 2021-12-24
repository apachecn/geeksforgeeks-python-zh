# Python |给定字符串中子字符串的频率

> 原文:[https://www . geesforgeks . org/python-给定字符串中的子字符串出现频率/](https://www.geeksforgeeks.org/python-frequency-of-substring-in-given-string/)

在一个字符串中寻找一个子串有很多方法。但是有时候，我们只是想知道一个特定的子串在一个字符串中出现了多少次。让我们讨论执行这项任务的某些方式。

**方法#1:使用`count()`**
这是一个相当简单的方法，在其中执行这个任务。它只是计算作为参数传递的字符串中出现的子字符串。

```
# Python3 code to demonstrate working of
# Frequency of substring in string 
# Using count()

# initializing string 
test_str = "GeeksforGeeks is for Geeks"

# initializing substring
test_sub = "Geeks" 

# printing original string 
print("The original string is : " + test_str)

# printing substring
print("The original substring : " + test_sub)

# using count()
# Frequency of substring in string
res = test_str.count(test_sub)

# printing result 
print("The frequency of substring in string is " + str(res))
```

**Output :**

```
The original string is : GeeksforGeeks is for Geeks
The original substring : Geeks
The frequency of substring in string is 3

```