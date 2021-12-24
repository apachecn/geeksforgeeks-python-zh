# Python |将字符串转换为二进制

> 原文:[https://www . geesforgeks . org/python-convert-string-to-binary/](https://www.geeksforgeeks.org/python-convert-string-to-binary/)

数据转换一直是广泛使用的工具，其中之一可以是字符串到其二进制等价物的转换。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`join() + ord() + format()`**
上述功能的组合可用于执行该特定任务。ord 函数将字符转换为它的等效 ASCII 码，format 函数将其转换为二进制数，join 函数用于将每个转换后的字符连接成一个字符串。

```py
# Python3 code to demonstrate working of
# Converting String to binary
# Using join() + ord() + format()

# initializing string 
test_str = "GeeksforGeeks"

# printing original string 
print("The original string is : " + str(test_str))

# using join() + ord() + format()
# Converting String to binary
res = ''.join(format(ord(i), '08b') for i in test_str)

# printing result 
print("The string after binary conversion : " + str(res))
```

**Output :**

```py
The original string is : GeeksforGeeks
The string after binary conversion : 01000111011001010110010101101011011100110110011001101111011100100100011101100101011001010110101101110011
```