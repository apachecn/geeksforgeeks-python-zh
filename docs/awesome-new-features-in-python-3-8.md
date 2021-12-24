# Python 3.8 中令人敬畏的新特性

> 原文:[https://www . geesforgeks . org/awesome-python 中的新功能-3-8/](https://www.geeksforgeeks.org/awesome-new-features-in-python-3-8/)

Python 是一种广泛使用的通用高级编程语言。它最初由吉多·范·罗苏姆在 1991 年设计，由 Python 软件基金会开发。它主要是为了强调代码的可读性而开发的，它的语法允许程序员用更少的代码行来表达概念。Python 是一种编程语言，可以让您快速工作并更高效地集成系统。
Python 3.8 比早期版本包含了许多小的改进。本文概述了 python 3.8
中最重要的增加和变化

#### <u>仅位置参数(/</u>

有一个新的函数参数语法“/”，表示某些函数参数必须按位置指定，不能用作关键字参数。“/”的添加提高了语言的一致性，并允许健壮的 API 设计。
**例:**

## 蟒蛇 3

```
# Arguments before / are considered
# as positional arguments only
def add(x, y, /, z = 0):
    a = x + y + z
    return a 

# Driver's code
print(add(2, 5))
print(add(2, 5, 7))
print(add(x = 2, y = 5))
```