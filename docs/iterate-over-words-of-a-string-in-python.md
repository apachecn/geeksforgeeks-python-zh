# 在 Python 中迭代字符串的单词

> 原文:[https://www . geesforgeks . org/iterate-over-words-of-a-string-in-python/](https://www.geeksforgeeks.org/iterate-over-words-of-a-string-in-python/)

给定一个由许多由空格分隔的单词组成的字符串，编写一个 Python 程序来迭代这些单词。

**示例:**

> **输入:** str = "GeeksforGeeks 是极客的计算机科学入口"
> **输出:**
> 极客 forGeeks
> 是
> 一个
> 计算机
> 科学
> 入口
> 为
> 极客准备的
> 
> **输入:** str = "极客为极客"
> T3】输出:T5】极客
> 为
> 极客

**方法 1:** 使用`split()`

使用`split()`函数，我们可以将字符串分割成一个单词列表，如果你想完成这个特殊的任务，这是最通用和推荐的方法。但缺点是在字符串包含标点符号的情况下会失败。

```
# Python3 code to demonstrate  
# to extract words from string  
# using split() 

# initializing string   
test_string = "GeeksforGeeks is a computer science portal for Geeks"

# printing original string 
print ("The original string is : " +  test_string) 

# using split() 
# to extract words from string 
res = test_string.split() 

# printing result 
print ("\nThe words of string are")
for i in res:
    print(i)
```

**输出:**

```
The original string is : GeeksforGeeks is a computer science portal for Geeks

The words of string are
GeeksforGeeks
is
a
computer
science
portal
for
Geeks

```

**方法二:**使用`re.findall()`

如上所述，在包含所有特殊字符和标点符号的情况下，使用拆分在字符串中查找单词的传统方法可能会失败，因此需要正则表达式来执行此任务。`findall()`函数在过滤字符串并提取忽略标点符号的单词后返回列表。

```
# Python3 code to demonstrate  
# to extract words from string  
# using regex( findall() ) 
import re 

# initializing string   
test_string = "GeeksforGeeks is a computer science portal for Geeks !!!"

# printing original string 
print ("The original string is : " +  test_string) 

# using regex( findall() ) 
# to extract words from string 
res = re.findall(r'\w+', test_string) 

# printing result 
print ("\nThe words of string are")
for i in res:
    print(i)
```

**输出:**

```
The original string is : GeeksforGeeks is a computer science portal for Geeks!!!

The words of string are
GeeksforGeeks
is
a
computer
science
portal
for
Geeks

```