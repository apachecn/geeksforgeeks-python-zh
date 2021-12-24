# 在 python 中找到列表的平均值

> 原文:[https://www.geeksforgeeks.org/find-average-list-python/](https://www.geeksforgeeks.org/find-average-list-python/)

先决条件: [sum()函数](https://www.geeksforgeeks.org/sum-function-python/)、 [len()函数](https://www.geeksforgeeks.org/list-methods-in-python-set-1-in-not-in-len-min-max/)、 [round()函数、](https://www.geeksforgeeks.org/round-function-python/)T6】reduce()、T8】lambda、和 [mean()](https://www.geeksforgeeks.org/statistical-functions-python-set-1averages-measure-central-location/) 。

给定一个数字列表，任务是找出该列表的平均值。平均值是元素的总和除以元素的数量。

示例:

```
Input : [4, 5, 1, 2, 9, 7, 10, 8]
Output : Average of the list = 5.75
Explanation:
Sum of the elements is 4+5+1+2+9+7+10+8 = 46
and total number of elements is 8.
So average is 46 / 8 = 5.75

Input : [15, 9, 55, 41, 35, 20, 62, 49]
Output : Average of the list = 35.75
Explanation:
Sum of the elements is 15+9+55+41+35+20+62+49 = 286
and total number of elements is 8.
So average is 46 / 8 = 35.75

```

**Using sum()**

在 Python 中，我们只需使用 **sum()** 和 **len()** 函数就可以找到列表的平均值。

*   **sum ()** : We can get the sum of the list by using the sum () function.
*   **len ()** : The len () function is used to obtain the length or number of elements in the list.

```
# Python program to get average of a list
def Average(lst):
    return sum(lst) / len(lst)

# Driver Code
lst = [15, 9, 55, 41, 35, 20, 62, 49]
average = Average(lst)

# Printing average of the list
print("Average of the list =", round(average, 2))
```

输出:

```
Average of the list = 35.75

```

**使用 reduce()和 lambda**

我们可以使用 reduce()来减少循环，并通过使用 lambda 函数来计算列表的总和。如上所述，我们使用 len()来计算长度。

```
# Python program to get average of a list
# Using reduce() and lambda 

# importing reduce()
from functools import reduce

def Average(lst):
    return reduce(lambda a, b: a + b, lst) / len(lst)

# Driver Code
lst = [15, 9, 55, 41, 35, 20, 62, 49]
average = Average(lst)

# Printing average of the list
print("Average of the list =", round(average, 2))
```

输出:

```
Average of the list = 35.75

```

**使用平均值()**

内置函数 mean()可用于计算列表的平均值。

```
# Python program to get average of a list
# Using mean()

# importing mean()
from statistics import mean

def Average(lst):
    return mean(lst)

# Driver Code
lst = [15, 9, 55, 41, 35, 20, 62, 49]
average = Average(lst)

# Printing average of the list
print("Average of the list =", round(average, 2))
```

输出:

```
Average of the list = 35.75

```