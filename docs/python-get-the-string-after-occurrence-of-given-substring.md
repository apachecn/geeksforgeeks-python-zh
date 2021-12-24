# Python |获取给定子串

出现后的字符串

> 原文:[https://www . geesforgeks . org/python-给定子串出现后获取字符串/](https://www.geeksforgeeks.org/python-get-the-string-after-occurrence-of-given-substring/)

有时，除了找到子字符串，我们可能还需要获取在找到子字符串后出现的字符串。让我们讨论执行这项任务的某些方法。

**方法#1:使用`partition()`**
分区函数可以用来执行这个任务，在这个任务中，我们只返回分区词之后出现的那部分分区。

```
# Python3 code to demonstrate
# Get String after substring occurrence
# using partition()

# initializing string 
test_string = "GeeksforGeeks is best for geeks"

# initializing split word
spl_word = 'best'

# printing original string 
print("The original string : " + str(test_string))

# printing split string 
print("The split string : " + str(spl_word))

# using partition()
# Get String after substring occurrence
res = test_string.partition(spl_word)[2]

# print result
print("String after the substring occurrence : " + res)
```

**Output :**

```
The original string : GeeksforGeeks is best for geeks
The split string : best
String after the substring occurrence :  for geeks

```