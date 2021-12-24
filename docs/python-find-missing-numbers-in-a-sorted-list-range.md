# Python |在排序列表范围内查找缺失的数字

> 原文:[https://www . geesforgeks . org/python-在排序列表中查找缺失的数字-范围/](https://www.geeksforgeeks.org/python-find-missing-numbers-in-a-sorted-list-range/)

给定一系列整数排序列表，中间缺少一些整数，编写一个 Python 程序来查找所有缺少的整数。

**示例:**

```
Input : [1, 2, 4, 6, 7, 9, 10]
Output : [3, 5, 8]

Input : [5, 6, 10, 11, 13]
Output : [7, 8, 9, 12]

```

**方法一:**列表理解

```
# Python3 program to Find missing 
# integers in list

def find_missing(lst):
    return [x for x in range(lst[0], lst[-1]+1) 
                               if x not in lst]

# Driver code
lst = [1, 2, 4, 6, 7, 9, 10]
print(find_missing(lst))
```

**Output:**

```
[3, 5, 8]

```

**方法 2 :** 使用 *zip()* 列出理解

```
# Python3 program to Find missing 
# integers in list

def find_missing(lst):
    return [i for x, y in zip(lst, lst[1:]) 
        for i in range(x + 1, y) if y - x > 1]

# Driver code
lst = [1, 2, 4, 6, 7, 9, 10]
print(find_missing(lst))
```

**Output:**

```
[3, 5, 8]

```

**方法三:**使用*设定*

Python 集合的使用是一种高效而巧妙的方法，可以找到列表中缺失的数字。我们将列表转换为集合，并简单地输出该集合与包含范围从 *min(lst)* 和 *max(lst)* 的整数的集合之间的差异。

```
# Python3 program to Find missing 
# integers in list

def find_missing(lst):
    return sorted(set(range(lst[0], lst[-1])) - set(lst))

# Driver code
lst = [1, 2, 4, 6, 7, 9, 10]
print(find_missing(lst))
```

**Output:**

```
[3, 5, 8]

```

**方法#4 :** 使用*区别()*

这与上一个方法类似，只是略有不同，我们可以使用 Python *difference()* 方法，而不是使用“-”运算符来查找两个集合之间的差异。

```
# Python3 program to Find missing 
# integers in list

def find_missing(lst):
    start = lst[0]
    end = lst[-1]
    return sorted(set(range(start, end + 1)).difference(lst))

# Driver code
lst = [1, 2, 4, 6, 7, 9, 10]
print(find_missing(lst))
```

**Output:**

```
[3, 5, 8]

```