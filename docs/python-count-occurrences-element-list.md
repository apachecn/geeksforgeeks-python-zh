# Python |计算列表中某个元素的出现次数

> 原文:[https://www . geesforgeks . org/python-count-occurs-element-list/](https://www.geeksforgeeks.org/python-count-occurrences-element-list/)

给定 Python 中的一个列表和一个数字 x，计算 x 在给定列表中出现的次数。
示例:

```py
Input : lst = [15, 6, 7, 10, 12, 20, 10, 28, 10]
         x = 10
Output : 3 
10 appears three times in given list.

Input : lst = [8, 6, 8, 10, 8, 20, 10, 8, 8]
        x = 16
Output : 0
```

**方法 1(简单方法)**
我们保留一个计数器，如果在列表中找到所需的元素，该计数器就会不断增加。

## 蟒蛇 3

```py
# Python code to count the number of occurrences
def countX(lst, x):
    count = 0
    for ele in lst:
        if (ele == x):
            count = count + 1
    return count

# Driver Code
lst = [8, 6, 8, 10, 8, 20, 10, 8, 8]
x = 8
print('{} has occurred {} times'.format(x, countX(lst, x)))
```

```py
Output:
8 has occurred 5 times
```

**方法二(使用 count())**
思路是使用[列表方法 count()](https://www.geeksforgeeks.org/list-methods-python/) 来统计出现次数。

## 蟒蛇 3

```py
# Python code to count the number of occurrences
def countX(lst, x):
    return lst.count(x)

# Driver Code
lst = [8, 6, 8, 10, 8, 20, 10, 8, 8]
x = 8
print('{} has occurred {} times'.format(x, countX(lst, x)))
```

```py
Output:
8 has occurred 5 times 
```

**方法 2(使用 Counter())**
Counter 方法返回一个字典，所有元素作为键值对出现，其中 key 是元素，value 是该元素出现的次数。

## 蟒蛇 3

```py
from collections import Counter

# declaring the list
l = [1, 1, 2, 2, 3, 3, 4, 4, 5, 5]

# driver program
x = 3
d = Counter(l)
print('{} has occurred {} times'.format(x, d[x]))
```

```py
Output:
3 has occurred 2 times
```