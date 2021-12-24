# Python |获取给定字符串的所有子字符串

> 原文:[https://www . geesforgeks . org/python-get-all-substrings-of-given-string/](https://www.geeksforgeeks.org/python-get-all-substrings-of-given-string/)

有许多问题需要我们获取字符串的所有子字符串。这种特殊的实用程序在竞争性编程中非常流行，用人手解决这个问题总是很方便。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解+字符串切片**
列表理解和字符串切片的结合可以用来执行这个特定的任务。这只是执行这个任务的蛮力方法。

```py
# Python3 code to demonstrate working of
# Get all substrings of string
# Using list comprehension + string slicing

# initializing string 
test_str = "Geeks"

# printing original string 
print("The original string is : " + str(test_str))

# Get all substrings of string
# Using list comprehension + string slicing
res = [test_str[i: j] for i in range(len(test_str))
          for j in range(i + 1, len(test_str) + 1)]

# printing result 
print("All substrings of string are : " + str(res))
```

**Output :**

> 原来的字符串是:Geeks
> 字符串的所有子字符串都是:['G '，' Ge '，' Gee '，' Geek '，' Geeks '，' e '，' ee '，' eek '，' e '，' ek '，' eks '，' k '，' ks '，' s']