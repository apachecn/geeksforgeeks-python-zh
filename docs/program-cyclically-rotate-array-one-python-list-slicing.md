# Python 中循环旋转一个数组的程序|列表切片

> 原文:[https://www . geesforgeks . org/program-cyclic-rotate-array-one-python-list-slicing/](https://www.geeksforgeeks.org/program-cyclically-rotate-array-one-python-list-slicing/)

给定一个数组，将该数组顺时针旋转 1。

示例:

```py
Input:  arr = [1, 2, 3, 4, 5]
Output: arr = [5, 1, 2, 3, 4]

```

这个问题我们已经有了解决方案，请参考[程序，通过一个](https://www.geeksforgeeks.org/c-program-cyclically-rotate-array-one/)链接循环旋转一个数组。我们将使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)在 python 中快速解决这个问题。方法很简单，只需删除列表中的最后一个元素，并将其追加到剩余列表的前面。

```py
# Program to cyclically rotate an array by one

def cyclicRotate(input):

     # slice list in two parts and append
     # last element in front of the sliced list

     # [input[-1]] --> converts last element pf array into list
     # to append in front of sliced list

     # input[0:-1] --> list of elements except last element
     print ([input[-1]] + input[0:-1])

# Driver program
if __name__ == "__main__":
    input = [1, 2, 3, 4, 5]
    cyclicRotate(input)
```

输出:

```py
[5, 1, 2, 3, 4]

```