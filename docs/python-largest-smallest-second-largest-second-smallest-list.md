# Python |列表中最大、最小、第二大、第二小

> 原文:[https://www . geesforgeks . org/python-最大-最小-第二大-第二小-列表/](https://www.geeksforgeeks.org/python-largest-smallest-second-largest-second-smallest-list/)

因为与其他编程语言不同，Python 没有数组，而是有列表。与数组相比，使用列表更加容易和舒适。此外，Python 巨大的内置功能使任务变得更加容易。因此，使用这些技术，让我们尝试在给定的列表中找到数字的不同范围。
示例:

```py
Input : list = [12, 45, 2, 41, 31, 10, 8, 6, 4]
Output : 
Largest element is: 45
Smallest element is: 2
Second Largest element is: 41
Second Smallest element is: 4

Input : list = [22, 85, 62, 40, 55, 12, 39, 2, 43]
Output :
Largest element is: 85
Smallest element is: 2
Second Largest element is: 62
Second Smallest element is: 12

```

方法很简单。Python 允许我们使用 list()函数对列表进行排序。利用这个，我们可以在一个列表中找到不同范围的数字，从那里开始，经过排序。像第一个位置必须包含最小的元素，最后一个元素必须包含最大的元素。

```py
# Python prog to illustrate the following in a list
def find_len(list1):
    length = len(list1)
    list1.sort()
    print("Largest element is:", list1[length-1])
    print("Smallest element is:", list1[0])
    print("Second Largest element is:", list1[length-2])
    print("Second Smallest element is:", list1[1])

# Driver Code
list1=[12, 45, 2, 41, 31, 10, 8, 6, 4]
Largest = find_len(list1)
```

**Output:**

```py
Largest element is: 45
Smallest element is: 2
Second Largest element is: 41
Second Smallest element is: 4

```

下面是另一个传统的计算方法。算法很简单，我们取一个数字，与列表中的所有其他数字进行比较，得到最大、最小、第二大和第二小的元素。

```py
# Python program to find largest, smallest, 
# second largest and second smallest in a
# list with complexity O(n)
def Range(list1): 
    largest = list1[0] 
    lowest = list1[0] 
    largest2 = None
    lowest2 = None
    for item in list1[1:]:     
        if item > largest: 
            largest2 = largest
            largest = item 
        elif largest2 == None or largest2 < item: 
            largest2 = item 
        if item < lowest: 
            lowest2 = lowest
            lowest = item 
        elif lowest2 == None or lowest2 > item: 
            lowest2 = item 

    print("Largest element is:", largest) 
    print("Smallest element is:", lowest) 
    print("Second Largest element is:", largest2) 
    print("Second Smallest element is:", lowest2) 

# Driver Code
list1 = [12, 45, 2, 41, 31, 10, 8, 6, 4]
Range(list1)
```

**Output:**

```py
Largest element is: 45
Smallest element is: 2
Second Largest element is: 41
Second Smallest element is: 4

```