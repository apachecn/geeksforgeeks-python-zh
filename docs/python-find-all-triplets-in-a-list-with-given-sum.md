# Python |在给定总和的列表中查找所有三元组

> 原文:[https://www . geesforgeks . org/python-查找列表中所有给定总和的三元组/](https://www.geeksforgeeks.org/python-find-all-triplets-in-a-list-with-given-sum/)

给定一个整数列表，编写一个 Python 程序来查找所有加起来等于给定整数“k”的三元组。

**示例:**

```
Input : [1, 2, 3, 4, 5, 6, 7, 8, 9, 10], k = 10
Output : [(1, 5, 4), (1, 6, 3), (1, 7, 2), (2, 5, 3)]

Input : [12, 3, 6, 1, 6, 9], k = 24
Output : [(12, 6, 6), (12, 9, 3)]

```

**方法#1 :** 朴素(使用集合)
在这种方法中，我们使用两个 for 循环。第一个循环设置第一个元素，另一个循环检查包括第一个元素的其他两个元素是否加起来为 k。这种方法需要**0(n<sup>2</sup>)**的时间复杂度。

```
# Python3 program to Find total number 
# of triplets in a temp_list with given k

def findTriplets(lst, k):
    triplet_count = 0
    final_temp_list =[]

    for i in range(0, len(lst)-1): 

        s = set() 
        temp_list = []

        # Adding first element
        temp_list.append(lst[i])

        curr_k = k - lst[i] 

        for j in range(i + 1, len(lst)): 

            if (curr_k - lst[j]) in s: 
                triplet_count += 1

                # Adding second element
                temp_list.append(lst[j])

                # Adding third element
                temp_list.append(curr_k - lst[j])

                # Appending tuple to the final list
                final_temp_list.append(tuple(temp_list))
                temp_list.pop(2)
                temp_list.pop(1)
            s.add(lst[j])

    return final_temp_list

# Driver Code
lst = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
k = 10
print(findTriplets(lst, k))
```

**Output:**

```
[(1, 5, 4), (1, 6, 3), (1, 7, 2), (2, 5, 3)]

```

**方法 2 :** 使用 itertools
Python itertools 模块提供*组合(iterable，r)* 功能。该工具从输入表中返回 r 长度的元素子序列。每次我们将 3 个元素组合在一起，检查它们的总和是否为 k。

```
# Python3 program to Find total number 
# of  triplets in a list with given sum
from itertools import combinations

def findTriplets(lst, key):

    def valid(val):
        return sum(val) == key

    return list(filter(valid, list(combinations(lst, 3))))

# Driver Code
lst = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print(findTriplets(lst, 10))
```

**Output:**

```
[(1, 2, 7), (1, 3, 6), (1, 4, 5), (2, 3, 5)]

```