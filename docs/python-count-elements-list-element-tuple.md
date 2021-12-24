# Python |对列表中的元素进行计数，直到一个元素成为元组

> 原文:[https://www . geesforgeks . org/python-count-elements-list-element-tuple/](https://www.geeksforgeeks.org/python-count-elements-list-element-tuple/)

在这个问题中，我们需要接受一个列表。列表可以有嵌套元组。我们需要计算列表中的元素，直到遇到元组。

示例:

```
Input : [4, 5, 6, 10, (1, 2, 3), 11, 2, 4]
Output : 4

Input : [4, (5, 6), 10, (1, 2, 3), 11, 2, 4]
Output : 1

```

在本程序中，我们将使用 *isinstance()* 的概念来验证我们在计数路径中是否遇到元组。有关 isinstance()的详细指南，请访问 Python 中的[is instance](https://www.geeksforgeeks.org/type-isinstance-python/)。

```
# Python program to count the items
# until a list is encountered
def Count(li):
    counter = 0
    for num in li:
        if isinstance(num, tuple):
            break
        counter = counter + 1
    return counter

# Driver Code
li = [4, 5, 6, 10, (1, 2, 3), 11, 2, 4]
print(Count(li))
```

输出:

```
4

```