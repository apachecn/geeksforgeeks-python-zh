# 在 Python 中计数数组中不同的元素

> 原文:[https://www . geeksforgeeks . org/count-python 数组中的不同元素/](https://www.geeksforgeeks.org/count-distinct-elements-in-an-array-in-python/)

给定一个未排序的数组，计算其中所有不同的元素。

**例:**

```py
Input : arr[] = {10, 20, 20, 10, 30, 10} 
Output : 3

Input : arr[] = {10, 20, 20, 10, 20}
Output : 2

```

对于这篇文章，我们已经有了解决方案。我们可以使用[计数器](https://www.geeksforgeeks.org/counters-in-python-set-2-accessing-counters/)方法在 Python3 中解决这个问题。

```py
from collections import Counter

def countDistinct(arr):

    # counter method gives dictionary of elements in list
    # with their corresponding frequency.
    # using keys() method of dictionary data structure
    # we can count distinct values in array
    return len(Counter(arr).keys())    

if __name__=="__main__":
    arr = [10, 20, 20, 10, 30, 10]
    print (countDistinct(arr))
```