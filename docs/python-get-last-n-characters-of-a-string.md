# Python–获取字符串的最后 N 个字符

> 原文:[https://www . geesforgeks . org/python-get-last-n-characters-of-a-string/](https://www.geeksforgeeks.org/python-get-last-n-characters-of-a-string/)

给定一个字符串和一个整数 N，任务是编写一个 python 程序来打印字符串的最后 N 个字符。

**示例:**

> **输入:**极客为极客！；N = 4
> 
> **输出:**例！
> 
> **说明:**给定的字符串是极客为极客！最后 4 个字符是 eks！。
> 
> **输入:**PYTHON；N=1
> 
> **输出:** N
> 
> **说明:**给定的字符串是 PYTHON，最后一个字符是 n。

**方法 1:** 使用[循环](https://www.geeksforgeeks.org/loops-in-python/)获取给定字符串的最后 N 个字符。

## 蟒蛇 3

```py
# get input
Str = "Geeks For Geeks!"
N = 4

# print the string
print(Str)

# iterate loop
while(N > 0):

  # print character
    print(Str[-N], end='')

    # decrement the value of N
    N = N-1
```

**输出:**

```py
Geeks For Geeks!
eks!
```

**方法二:**使用[列表切片](https://www.geeksforgeeks.org/python-list-slicing/)打印给定字符串的最后 n 个字符。

## 计算机编程语言

```py
# get input
Str = "Geeks For Geeks!"
N = 4

# print the string
print(Str)

# get length of string
length = len(Str)

# create a new string of last N characters
Str2 = Str[length - N:]

# print Last N characters
print(Str2)
```

**输出:**

```py
Geeks For Geeks!
eks!
```