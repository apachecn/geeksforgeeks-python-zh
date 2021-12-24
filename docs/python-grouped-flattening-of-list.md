# Python |列表分组扁平化

> 原文:[https://www . geeksforgeeks . org/python-分组-列表扁平化/](https://www.geeksforgeeks.org/python-grouped-flattening-of-list/)

展平列表的问题很常见，但有时，我们需要以分组的方式执行展平，即获取大小为 K 的子列表并将其展平。这个特殊的实用程序在许多领域都有用例，包括网络开发和日常编程。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+列表切片**
这个问题可以通过使用列表理解并应用列表切片来限制分组来解决，列表绑定作为列表理解逻辑的一部分来完成。

```
# Python3 code to demonstrate 
# group flattening of list 
# using list comprehension + list slicing

# initializing list of lists
test_list = [[1, 3], [3, 4], [6, 5], [4, 5], [7, 6], [7, 9]]

# printing original list 
print("The original list : " +  str(test_list))

# declaring K 
K = 3

# using list comprehension + list slicing
# group flattening of list 
res = [[i for sub in test_list[j : j + K] for i in sub]
                  for j in range(0, len(test_list), K)]

# printing result 
print("The grouped flattened list :  " + str(res))
```

**Output :**

```
The original list : [[1, 3], [3, 4], [6, 5], [4, 5], [7, 6], [7, 9]]
The grouped flattened list :  [[1, 3, 3, 4, 6, 5], [4, 5, 7, 6, 7, 9]]

```