# Python–查找包含字母和数字的单词

> 原文:[https://www . geesforgeks . org/python-find-words-with-both-alphabets-and-numbers/](https://www.geeksforgeeks.org/python-find-words-with-both-alphabets-and-numbers/)

有时，在使用 Python 字符串时，我们可能会遇到这样的问题，即我们需要提取同时包含数字和字母的某些单词。这种问题可能发生在许多领域，如学校编程和网络开发。让我们讨论执行这项任务的某些方法。

**方法#1:使用`any() + isdigit() + isalpha()`**
上述功能的组合可用于执行该任务。在本文中，我们迭代所有单词，并使用`isdigit()`和 isalpha()检查所需的组合。

```
# Python3 code to demonstrate working of 
# Words with both alphabets and numbers
# Using isdigit() + isalpha() + any()

# initializing string
test_str = 'geeksfor23geeks is best45 for gee34ks and cs'

# printing original string
print("The original string is : " + test_str)

# Words with both alphabets and numbers
# Using isdigit() + isalpha() + any()
res = []
temp = test_str.split()
for idx in temp:
    if any(chr.isalpha() for chr in idx) and any(chr.isdigit() for chr in idx):
        res.append(idx)

# printing result 
print("Words with alphabets and numbers : " + str(res)) 
```

**Output :**

> 原始字符串为:geesfor23 geeks best45 表示 gee34ks 和 cs
> 带有字母和数字的单词:[' geesfor23 geeks '，' best 45 '，' gee34ks']