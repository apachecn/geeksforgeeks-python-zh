# 打印中的 Python 结束参数()

> 原文:[https://www . geesforgeks . org/gfact-50-python-end-print 中的参数/](https://www.geeksforgeeks.org/gfact-50-python-end-parameter-in-print/)

默认情况下，python 的 print()函数以换行符结束。有 C/C++背景的程序员可能会想，没有换行符怎么打印。

Python 的 print()函数附带了一个名为“end”的参数。默认情况下，该参数的值为' \n '，即新的行字符。使用此参数，可以用任何字符/字符串结束打印语句。

```py
# This Python program must be run with
# Python 3 as it won't work with 2.7.

# ends the output with a <space> 
print("Welcome to" , end = ' ') 
print("GeeksforGeeks", end = ' ')
```

输出:

```py
Welcome to GeeksforGeeks
```

再来一个程序来演示结束参数的工作。

```py
# This Python program must be run with
# Python 3 as it won't work with 2.7.

# ends the output with '@'
print("Python" , end = '@') 
print("GeeksforGeeks")
```

输出:

```py
Python@GeeksforGeeks
```

本文由 **Ankit Bindal** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论