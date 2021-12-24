# Python |获取字符串中匹配的子字符串

> 原文:[https://www . geesforgeks . org/python-get-matching-substrings-in-string/](https://www.geeksforgeeks.org/python-get-matching-substrings-in-string/)

对字符串中单个子字符串的测试已经讨论过多次。但是有时，我们有一个潜在子字符串的列表，并检查哪些子字符串作为子字符串出现在目标字符串中。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
使用列表理解是执行这个特定任务的幼稚而蛮力的方法。在此方法中，我们尝试使用“In”运算符获取匹配字符串，并将其存储在新列表中。

```py
# Python3 code to demonstrate working of
# Get matching substrings in string
# Using list comprehension

# initializing string 
test_str = "GfG is good website"

# initializing potential substrings
test_list = ["GfG", "site", "CS", "Geeks", "Tutorial" ]

# printing original string 
print("The original string is : " + test_str)

# printing potential strings list
print("The original list is : " + str(test_list))

# using list comprehension
# Get matching substrings in string
res = [sub for sub in test_list if sub in test_str]

# printing result 
print("The list of found substrings : " + str(res))
```

**Output :**

```py
The original string is : GfG is good website
The original list is : ['GfG', 'site', 'CS', 'Geeks', 'Tutorial']
The list of found substrings : ['GfG', 'site']

```