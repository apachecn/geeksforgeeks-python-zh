# Python |仅使用字母提取字符串

> 原文:[https://www . geesforgeks . org/python-extract-strings-with-only-alphabets/](https://www.geeksforgeeks.org/python-extract-strings-with-only-alphabets/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要只提取那些只包含字母的字符串，而丢弃那些包含数字的字符串。这在日常编程和 web 开发领域都有应用。让我们讨论执行这项任务的某些方法。

**方法一:使用`isalpha()` +列表理解**
以上功能的组合可以用来执行此任务。在本文中，我们只使用 isalpha()提取字母字符串，并使用列表理解编译整个逻辑。

```
# Python3 code to demonstrate working of 
# Extract Alphabet only Strings
# Using isalpha() + list comprehension

# initializing list
test_list = ['gfg', 'is23', 'best', 'for2', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

# Extract Alphabet only Strings
# Using isalpha() + list comprehension
res = [sub for sub in test_list if sub.isalpha()]

# printing result 
print("Strings after filtering : " + str(res)) 
```

**Output :**

```
The original list is : ['gfg', 'is23', 'best', 'for2', 'geeks']
Strings after filtering : ['gfg', 'best', 'geeks']

```