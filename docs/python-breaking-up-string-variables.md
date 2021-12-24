# Python–分解字符串变量

> 原文:[https://www . geeksforgeeks . org/python-分解-字符串-变量/](https://www.geeksforgeeks.org/python-breaking-up-string-variables/)

**先决条件:**T2

给定一个字符串，任务是编写一个 Python 程序来分解字符串并创建单独的元素。

> **输入:**geeks forges
> T3】输出: [ 'G '，' e '，' e '，' k '，' s '，' F '，' o '，' r '，' G '，' e '，' e '，' k '，' s' ]
> 
> **输入:**计算机
> T3】输出: [ 'C '，' o '，' m '，' p '，' u '，' t '，' e '，' r']

下面是一些完成上述任务的方法。

**方法#1:** 使用[连接()](https://www.geeksforgeeks.org/join-function-python/)功能

join()方法提供了一种从可迭代对象创建字符串的灵活方法。它通过字符串分隔符(在其上调用 join()方法的字符串)连接可迭代表的每个元素(如列表、字符串和元组)，并返回连接的字符串。

## 蟒蛇 3

```
a = "GeeksForGeeks"

split_string = list(''.join(a))

print(split_string)
```

**输出:**

> [‘G’、‘e’、‘e’、‘k’、‘s’、‘F’、‘o’、‘r’、‘G’、‘e’、‘e’、‘k’、‘s’]

**方法 2:** 使用[进行循环](https://www.geeksforgeeks.org/python-for-loops/)

## 蟒蛇 3

```
a = "GeeksForGeeks"

res = [i for ele in a for i in ele]

print(res)
```

**输出:**

> [‘G’、‘e’、‘e’、‘k’、‘s’、‘F’、‘o’、‘r’、‘G’、‘e’、‘e’、‘k’、‘s’]

**方法#3:** 使用[链。from_iterable()](https://www.geeksforgeeks.org/python-itertools-chain-from_iterable/)

## 蟒蛇 3

```
from itertools import chain

a = "GeeksForGeeks"

# using chain.from_iterable()
# to convert list of string and characters
# to list of characters
res = list(chain.from_iterable(a))

# printing result
print(str(res))
```

**输出:**

> [‘G’、‘e’、‘e’、‘k’、‘s’、‘F’、‘o’、‘r’、‘G’、‘e’、‘e’、‘k’、‘s’]