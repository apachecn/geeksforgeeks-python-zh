# Python |将数组反转到给定位置

> 原文:[https://www . geesforgeks . org/pyhton-reverse-array-up-给定位置/](https://www.geeksforgeeks.org/pyhton-reverse-array-upto-given-position/)

给定数组 arr[]和数组 k 中的一个位置，写一个函数名 reverse (a[]，k)，这样它就可以反转子数组 arr[0..k-1]。使用的额外空间应为 0(1)，时间复杂度应为 0(k)。

示例:

```py
Input: arr[] = {1, 2, 3, 4, 5, 6}
       k = 4

Output:  arr[] = {4, 3, 2, 1, 5, 6} 

```

此问题已有解决方案，请参考[将数组反转到给定位置](https://www.geeksforgeeks.org/reverse-an-array-upto-a-given-position/)链接。我们将在 Python 中快速解决这个问题。

```py
# Program to Reverse an array 
# upto a given position 

def reverseArrayUptoK(input, k):

    # reverse list starting from k-1 position 
    # and split remaining list after k
    # concat both parts and print
    # input[k-1::-1] --> generate list starting
    # from k-1 position element till first 
    # element in reverse order
    print (input[k-1::-1] + input[k:])

# Driver program
if __name__ == "__main__":
    input = [1, 2, 3, 4, 5, 6]
    k = 4
    reverseArrayUptoK(input, k)
```

输出:

```py
[4, 3, 2, 1, 5, 6]

```