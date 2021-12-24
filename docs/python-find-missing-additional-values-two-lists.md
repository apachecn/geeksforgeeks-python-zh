# Python |在两个列表中查找缺失值和附加值

> 原文:[https://www . geesforgeks . org/python-find-missing-additional-values-two-list/](https://www.geeksforgeeks.org/python-find-missing-additional-values-two-lists/)

给定两个列表，找出这两个列表中缺少的值和附加值。

示例:

```py
Input : list1 = [1, 2, 3, 4, 5, 6] 
        list2 = [4, 5, 6, 7, 8] 
Output : Missing values in list1 = [8, 7] 
         Additional values in list1 = [1, 2, 3] 
         Missing values in list2 = [1, 2, 3] 
         Additional values in list2 = [7, 8] 

Explanation: 

```

方法:为了找到列表 2 中缺失的元素，我们需要得到列表 1 和列表 2 的区别。要找到列表 2 的附加元素，请计算列表 2 与列表 1 的差异。
同样，在查找列表 1 的缺失元素时，计算列表 2 与列表 1 的差异。要找到列表 1 中的附加元素，请计算列表 1 和列表 2 的差异。

插入要设置的列表 1 和列表 2，然后使用集合中的差分函数得到所需答案。

先决条件: [Python 集差](https://www.geeksforgeeks.org/python-set-difference/)

```py
# Python program to find the missing 
# and additional elements 

# examples of lists
list1 = [1, 2, 3, 4, 5, 6]
list2 = [4, 5, 6, 7, 8]

# prints the missing and additional elements in list2 
print("Missing values in second list:", (set(list1).difference(list2)))
print("Additional values in second list:", (set(list2).difference(list1)))

# prints the missing and additional elements in list1
print("Missing values in first list:", (set(list2).difference(list1)))
print("Additional values in first list:", (set(list1).difference(list2)))
```

输出:

```py
Missing values in second list: {1, 2, 3}
Additional values in second list: {7, 8}
Missing values in first list: {7, 8}
Additional values in first list: {1, 2, 3}

```