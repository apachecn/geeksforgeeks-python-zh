# Python |通过字典交集找到三个排序数组中的公共元素

> 原文:[https://www . geesforgeks . org/python-dictionary-交集-find-common-elements-三排序-数组/](https://www.geeksforgeeks.org/python-dictionary-intersection-find-common-elements-three-sorted-arrays/)

给定三个按非递减顺序排序的数组，打印这些数组中的所有公共元素。

示例:

```py
Input:  ar1 = [1, 5, 10, 20, 40, 80]
        ar2 = [6, 7, 20, 80, 100]
        ar3 = [3, 4, 15, 20, 30, 70, 80, 120]
Output: [80, 20]

Input:  ar1 = [1, 5, 5]
        ar2 = [3, 4, 5, 5, 10]
        ar3 = [5, 5, 10, 20]
Output: [5, 5]

```

这个问题我们已经有了解决方案，请参考[找到三个排序数组中的公共元素](https://www.geeksforgeeks.org/find-common-elements-three-sorted-arrays/)链接。我们可以使用字典的**交集**在 python 中快速解决这个问题。方法很简单，

1.  首先使用 [Counter()](https://www.geeksforgeeks.org/counters-in-python-set-1/) 方法，将所有三个列表转换成以元素为键，以它们的频率为值的字典。
2.  现在对三个字典执行交集操作，这将导致我们的字典在三个数组列表中具有公共元素及其频率。

```py
# Function to find common elements in three
# sorted arrays
from collections import Counter

def commonElement(ar1,ar2,ar3):
     # first convert lists into dictionary
     ar1 = Counter(ar1)
     ar2 = Counter(ar2)
     ar3 = Counter(ar3)

     # perform intersection operation
     resultDict = dict(ar1.items() & ar2.items() & ar3.items())
     common = []

     # iterate through resultant dictionary
     # and collect common elements
     for (key,val) in resultDict.items():
          for i in range(0,val):
               common.append(key)

     print(common)

# Driver program
if __name__ == "__main__":
    ar1 = [1, 5, 10, 20, 40, 80]
    ar2 = [6, 7, 20, 80, 100]
    ar3 = [3, 4, 15, 20, 30, 70, 80, 120]
    commonElement(ar1,ar2,ar3)
```

输出:

```py
[80, 20]

```