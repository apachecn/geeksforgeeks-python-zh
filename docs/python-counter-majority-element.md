# Python 计数器|多数元素

> 原文:[https://www . geesforgeks . org/python-计数器-多数-元素/](https://www.geeksforgeeks.org/python-counter-majority-element/)

[**多数元素:**](https://www.geeksforgeeks.org/majority-element/) 大小为 n 的数组 A[]中的多数元素是出现次数超过 n/2 次的元素(因此最多有一个这样的元素)。

编写一个函数，该函数接受一个数组并发出多数元素(如果存在的话)，否则按如下方式输出 NONE:

示例:

```py
Input : 3 3 4 2 4 4 2 4 4
Output : 4 

Input : 3 3 4 2 4 4 2 4
Output : NONE

```

这个问题我们已经有了解决方案，请参考[多数元素](https://www.geeksforgeeks.org/majority-element/)链接。我们可以使用 [Counter(iterable)](https://www.geeksforgeeks.org/counters-in-python-set-1/) 函数在 Python 中快速解决这个问题。方法很简单，

1.  Use the **counter ()** method to convert the given list of elements into a dictionary, with elements as keys and their frequencies as values.
2.  Now walk through the whole dictionary and check the elements whose frequency follows the condition greater than (n/2), where n is the size of the list. That element will be the majority element.

```py
# Function to find majority element
from collections import Counter

def majority(arr):

    # convert array into dictionary
    freqDict = Counter(arr)

    # traverse dictionary and check majority element
    size = len(arr)
    for (key,val) in freqDict.items():
         if (val > (size/2)):
             print(key)
             return
    print('None')

# Driver program
if __name__ == "__main__":
    arr = [3,3,4,2,4,4,2,4,4] 
    majority(arr)
```

输出:

```py
4

```