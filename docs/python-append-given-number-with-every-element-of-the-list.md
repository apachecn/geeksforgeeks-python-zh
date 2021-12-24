# Python–在列表的每个元素中添加给定的数字

> 原文:[https://www . geeksforgeeks . org/python-用列表中的每个元素追加给定的数字/](https://www.geeksforgeeks.org/python-append-given-number-with-every-element-of-the-list/)

给定一个列表和一个数字，编写一个 Python 程序，将数字附加到列表的每个元素中。

**示例:**

> **输入= [1，2，3，4，5]**
> 
> **键= 5** (数字待定)
> 
> **输出= [1，5，2，5，3，5，4，5，5，5]**

以下是实现此功能的方法:

**方法 1:** *使用* [*进行循环*](https://www.geeksforgeeks.org/python-for-loops/)

## 计算机编程语言

```
input = [1, 2, 3, 4, 5]
key = 7

result = []
for ele in input:
    result.append(ele)
    result.append(key)

print(result)
```

**输出:**

```
[1, 7, 2, 7, 3, 7, 4, 7, 5, 7]
```

**方法二:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) *和*[*ITER tools . chain*](https://www.geeksforgeeks.org/python-itertools/)

## 计算机编程语言

```
import itertools

input = [1, 2, 3, 4, 5]
key = 7

result = list(itertools.chain(*[[ele, key] for ele in input]))

print(result)
```

**输出:**

```
[1, 7, 2, 7, 3, 7, 4, 7, 5, 7]
```

**方法三:** *使用* [*zip*](https://www.geeksforgeeks.org/zip-in-python/) *和* [*进行循环*](https://www.geeksforgeeks.org/python-for-loops/)

## 计算机编程语言

```
input = [1, 2, 3, 4, 5]
key = 7

result = []
for x, y in zip(input, [key]*len(input)):
    result.extend([x, y])

print(result)
```

**输出:**

```
[1, 7, 2, 7, 3, 7, 4, 7, 5, 7]
```