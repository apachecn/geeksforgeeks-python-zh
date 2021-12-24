# Python |计算元组中元素的出现次数

> 原文:[https://www . geesforgeks . org/python-count-occurs-element-tuple/](https://www.geeksforgeeks.org/python-count-occurrences-element-tuple/)

在这个程序中，我们需要接受一个元组，然后找到一个条目在元组中出现的次数。这可以通过各种方式来实现，但是在本文中，我们将看到如何使用简单的方法来实现这一点，以及如何使用内置函数来解决这个问题。

示例:

```py
Tuple: (10, 8, 5, 2, 10, 15, 10, 8, 5, 8, 8, 2)

Input : 4
Output : 0 times

Input : 10
Output : 3 times

Input : 8
Output : 4 times

```

<font size="+0.5">**方法 1(简单方法):**</font>
我们保留一个计数器，如果在元组中找到所需的元素，该计数器就会不断增加。

```py
# Program to count the number of times an element
# Present in the list
def countX(tup, x):
    count = 0
    for ele in tup:
        if (ele == x):
            count = count + 1
    return count

# Driver Code
tup = (10, 8, 5, 2, 10, 15, 10, 8, 5, 8, 8, 2)
enq = 4
enq1 = 10
enq2 = 8
print(countX(tup, enq))
print(countX(tup, enq1))
print(countX(tup, enq2))
```

输出:

```py
0 times
3 times
4 times

```

<font size="+0.5">**方法二(使用 count()):**</font>
思路是用方法 count()来统计出现次数。

```py
# Program to count the number of times an element
# Present in the list
# Count function is used
def Count(tup, en):
    return tup.count(en)

# Driver Code
tup = (10, 8, 5, 2, 10, 15, 10, 8, 5, 8, 8, 2)
enq = 4
enq1 = 10
enq2 = 8
print(Count(tup, enq), "times")
print(Count(tup, enq1), "times")
print(Count(tup, enq2), "times")
```

输出:

```py
0 times
3 times
4 times

```