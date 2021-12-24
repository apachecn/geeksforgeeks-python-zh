# Python |前 N 个字母串构造

> 原文:[https://www . geesforgeks . org/python-first-n-letters-string-construction/](https://www.geeksforgeeks.org/python-first-n-letters-string-construction/)

有时，我们需要以不同的方式初始化字符串，而不是初始化空字符串。，我们可能需要用英文字母中的前 N 个字符初始化一个字符串。这可以在竞争性编程中得到应用。让我们讨论执行这项任务的某些方法。

**方法一:使用`join()` +列表理解**
该任务可以结合以上功能执行。连接函数可用于连接字符串，列表理解可执行添加 N 个数字的逻辑任务。

```py
# Python3 code to demonstrate
# First N letters string construction
# using join() + list comprehension

# initializing N 
N = 15

# using join() + list comprehension
# First N letters string construction
res = ''.join(['% c' % x for x in range(97, 97 + N)])

# print result
print("The string after construction : " + str(res))
```

**Output :**

```py
The string after construction : abcdefghijklmno

```