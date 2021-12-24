# Python |查找列表中最大元素的频率

> 原文:[https://www . geeksforgeeks . org/python-查找列表中最大元素的频率/](https://www.geeksforgeeks.org/python-find-frequency-of-largest-element-in-list/)

给定一个列表，任务是找到列表中最大元素的出现次数。
**例:**

```py
Input : [1, 2, 8, 5, 8, 7, 8]
Output :3

Input : [2, 9, 1, 3, 4, 5]
Output :1
```

**方法 1:** 最简单的方法是使用 max(list)函数找到列表中存在的最大元素，然后使用 for 循环遍历列表，找到列表中最大元素的出现频率。下面是实现。

## 蟒蛇 3

```py
# Python program to find the
# frequency of largest element

L = [1, 2, 8, 5, 8, 7, 8]

# print the  frequency of largest element
frequency = print(L.count(max(L)))

```

**输出:**

```py
3
```

**方法 2:** 使用集合。计数器()
一旦初始化，计数器就像字典一样被访问。此外，它不会引发键值错误(如果键值不存在)，取而代之的是该值的计数显示为 0。

## 蟒蛇 3

```py
# Python program to find the
# frequency of largest element

import collections

L = [1, 2, 8, 5, 8, 7, 8]

# find the largest element
largest = max(L)

# Storing the occurrences of each
# element of list in res
res = collections.Counter(L)

print(res[largest])
```

**输出:**

```py
3
```

**方法 3:** 使用字典
在这种方法中，每个元素的出现次数作为键值对存储在字典中，其中键是元素，值是频率。

## 蟒蛇 3

```py
# Python program to find the
# frequency of largest element

L = [1, 2, 8, 5, 8, 7, 8]
d= {}

# find the largest element
largest = max(L)

for i in L:
    if i in d:
        d[i] += 1
    else:
        d[i] = 1

print(d[largest])
```

**输出:**

```py
3
```