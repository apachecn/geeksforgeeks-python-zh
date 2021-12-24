# Python–从字符串中删除大写字母开头的单词

> 原文:[https://www . geesforgeks . org/python-消除-大写-字母-起始-单词-从字符串/](https://www.geeksforgeeks.org/python-eliminate-capital-letter-starting-words-from-string/)

有时，在使用 Python Strings 时，我们可能会遇到一个问题，需要删除所有以大写字母开头的单词。以大写字母开头的单词是专有名词，它们的出现对句子来说意味着不同的意思，有时可能是不受欢迎的。让我们讨论执行这项任务的某些方法。

> **输入** : test_str = 'GeeksforGeeks 最适合 Geeks '
> T3】输出:'最适合'
> 
> **输入** : test_str = 'GeeksforGeeks 最适合 Geeks '
> T3】输出【T4:"

**方法#1:使用`join() + split() + isupper()`**
以上功能的组合可以提供解决这个问题的方法之一。在本例中，我们使用 isupper()执行提取大写的单个字符串的任务，然后执行 join()以获得结果。

```
# Python3 code to demonstrate working of 
# Eliminate Capital Letter Starting words from String
# Using join() + split() + isupper()

# initializing string
test_str = 'GeeksforGeeks is Best for Geeks'

# printing original string
print("The original string is : " + str(test_str))

# Eliminate Capital Letter Starting words from String
# Using join() + split() + isupper()
temp = test_str.split()
res = " ".join([ele for ele in temp if not ele[0].isupper()])

# printing result 
print("The filtered string : " + str(res)) 
```

**Output :**

```
The original string is : GeeksforGeeks is Best for Geeks
The filtered string : is for

```

**方法 2:使用`regex()`**
使用正则表达式是解决这个问题的方法之一。在这里，我们使用适当的正则表达式提取所有大写的元素。

```
# Python3 code to demonstrate working of 
# Eliminate Capital Letter Starting words from String
# Using regex()
import re

# initializing string
test_str = 'GeeksforGeeks is Best for Geeks'

# printing original string
print("The original string is : " + str(test_str))

# Eliminate Capital Letter Starting words from String
# Using regex()
res = re.sub(r"\s*[A-Z]\w*\s*", " ", test_str).strip()

# printing result 
print("The filtered string : " + str(res)) 
```

**Output :**

```
The original string is : GeeksforGeeks is Best for Geeks
The filtered string : is for

```