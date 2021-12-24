# Python |查找列表中给定元素的频率之和

> 原文:[https://www . geesforgeks . org/python-查找列表中给定元素的频率总和/](https://www.geeksforgeeks.org/python-find-sum-of-frequency-of-given-elements-in-the-list/)

给定两个包含整数的列表，任务是找出第一个列表元素在第二个列表中的频率之和。

**示例:**

```
Input: list1 = [1, 2, 3]
       list2 = [2, 1, 2, 1, 3, 5, 2, 3]

Output: 7

Explanation:
No of time 1 occurring in list2 is :2
No of time 2 occurring in list2 is :3
No of time 3 occurring in list2 is :2
Sum = 2+3+2 = 7

```

以下是实现上述任务的一些方法。

**方法#1:** 使用`sum()`

```
# Python code to find sum of frequency of 
# element of first list in second list.

# List initialization
Input1 = [1, 2, 3]
Input2 = [2, 1, 2, 1, 3, 5, 2, 3]

# Using sum
Output = sum(Input2.count(elem) for elem in Input1)

# Printing output
print("Initial list are:", Input1, Input2)
print("Frequency is:", Output)
```

**Output:**

```
Initial list are: [1, 2, 3] [2, 1, 2, 1, 3, 5, 2, 3]
Frequency is: 7

```

**方法二:使用`sum()``Counter()`**

```
from collections import Counter

# List initialization
Input1 = [1, 2, 3]
Input2 = [2, 1, 2, 1, 3, 5, 2, 3]

temp = Counter(Input2)
Output = sum(temp[x] for x in Input1)

# Printing output
print("Initial list are:", Input1, Input2)
print("Frequency is:", Output)
```

**Output:**

```
Initial list are: [1, 2, 3] [2, 1, 2, 1, 3, 5, 2, 3]
Frequency is: 7

```