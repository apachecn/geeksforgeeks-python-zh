# Python–获取给定字符串中的第 n 个单词

> 原文:[https://www . geesforgeks . org/python-get-n th-word-in-given-string/](https://www.geeksforgeeks.org/python-get-nth-word-in-given-string/)

有时，在处理数据时，我们可能会遇到一个问题，需要获取字符串的第 n 个单词。这类问题在学校和日常编程中有许多应用。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环**
这是解决这个问题的一种方法。在这里，我们运行一个循环并检查空格。第 N 个字是有第 N-1 个空格的时候。我们回那个词。

```py
# Python3 code to demonstrate working of
# Get Nth word in String
# using loop

# initializing string 
test_str = "GFG is for Geeks"

# printing original string 
print("The original string is : " + test_str)

# initializing N 
N = 3

# Get Nth word in String
# using loop
count = 0
res = ""
for ele in test_str:
    if ele == ' ':
        count = count + 1
        if count == N:
            break
        res = ""
    else :
        res = res + ele

# printing result
print("The Nth word in String : " + res)
```

**Output :**

```py
The original string is : GFG is for Geeks
The Nth word in String : for

```