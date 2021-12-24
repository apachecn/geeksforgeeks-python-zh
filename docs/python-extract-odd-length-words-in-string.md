# Python |提取字符串中的奇数长度单词

> 原文:[https://www . geesforgeks . org/python-extract-奇数长度-字符串中的单词/](https://www.geeksforgeeks.org/python-extract-odd-length-words-in-string/)

有时，在使用 Python 时，我们可能会遇到一个问题，即我们需要从字符串中提取特定长度的单词。这可以是从字符串中提取奇数长度的单词。这可以应用于许多领域，包括日常编程。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们首先将字符串拆分成单词，然后执行迭代以获得奇数长度的单词。

```py
# Python3 code to demonstrate working of 
# Extract odd length words in String
# Using loop

# initializing string
test_str = "gfg is best of geeks"

# printing original string
print("The original string is : " + test_str)

# Extract odd length words in String
# Using loop
res = []
for ele in test_str.split():
    if len(ele) % 2 :
        res.append(ele)

# printing result 
print("The odd length strings are : " + str(res)) 
```

**Output :**

```py
The original string is : gfg is best of geeks
The odd length strings are : ['gfg', 'geeks']

```