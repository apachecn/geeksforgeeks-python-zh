# 在 Python 中打印给定整数数组的所有不同元素的程序|有序字典

> 原文:[https://www . geesforgeks . org/program-print-distinct-elements-given-integer-array-python-ordered-dictionary/](https://www.geeksforgeeks.org/program-print-distinct-elements-given-integer-array-python-ordered-dictionary/)

给定一个整数数组，打印数组中所有不同的元素。给定的数组可能包含重复项，输出应该只打印每个元素一次。给定的数组没有排序。

示例:

```
Input: arr[] = {12, 10, 9, 45, 2, 10, 10, 45}
Output: 12, 10, 9, 45, 2

Input: arr[] = {1, 2, 3, 4, 5}
Output: 1, 2, 3, 4, 5

Input: arr[] = {1, 1, 1, 1, 1}
Output: 1

```

此问题已有解决方案请参考[打印给定整数数组的所有不同元素](https://www.geeksforgeeks.org/print-distinct-elements-given-integer-array/)链接。我们将使用[有序字典](https://www.geeksforgeeks.org/ordereddict-in-python/)在 python 中快速解决这个问题。方法很简单，

1.  使用**ordereddct . from keys(iterable)**函数将数组转换为字典数据结构，它将任何 iterable 转换为字典，字典中的元素与它们在数组中出现的顺序相同。
2.  现在迭代完整的字典和打印键。

```
# Python program to print All Distinct
# Elements of a given integer array

from collections import OrderedDict

def printDistinct(input):
     # convert list into ordered dictionary
     ordDict = OrderedDict.fromkeys(input)

     # iterate through dictionary and get list of keys
     # list of keys will be resultant distinct elements 
     # in array
     result = [ key for (key, value) in ordDict.items() ]

     # concatenate list of elements with ', ' and print
     print (', '.join(map(str, result)))  

# Driver program
if __name__ == "__main__":
    input = [12, 10, 9, 45, 2, 10, 10, 45]
    printDistinct(input)
```

输出:

```
12, 10, 9, 45, 2

```