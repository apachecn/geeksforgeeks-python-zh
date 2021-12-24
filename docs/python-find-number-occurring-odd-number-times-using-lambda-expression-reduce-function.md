# Python |使用 Lambda 表达式查找出现奇数次的次数并减少函数

> 原文:[https://www . geesforgeks . org/python-find-number-occurrent-奇数-次数-使用-lambda-expression-reduce-function/](https://www.geeksforgeeks.org/python-find-number-occurring-odd-number-times-using-lambda-expression-reduce-function/)

给定一个正整数数组。所有的数字都出现偶数次，只有一个数字出现奇数次。求 O(n)时间&常数空间中的数。

示例:

```py
Input :  [1, 2, 3, 2, 3, 1, 3]
Output :  3

```

这个问题我们已经有解决方案了，请参考[找到出现奇数次的次数](https://www.geeksforgeeks.org/find-the-number-occurring-odd-number-of-times/)链接。我们将使用 [Reduce(表达式，可迭代)](https://www.geeksforgeeks.org/reduce-in-python/)方法在 python 中快速解决这个问题。

```py
# Python program to Find the Number 
# Occurring Odd Number of Times
# using Lambda expression and reduce function

from functools import reduce

def oddTimes(input):
     # write lambda expression and apply
     # reduce function over input list
     # until single value is left
     # expression reduces value of a ^ b into single value
     # a starts from 0 and b from 1
     # ((((((1 ^ 2)^3)^2)^3)^1)^3)
     print (reduce(lambda a, b: a ^ b, input))

# Driver program
if __name__ == "__main__":
    input = [1, 2, 3, 2, 3, 1, 3]
    oddTimes(input)
```

输出:

```py
3

```