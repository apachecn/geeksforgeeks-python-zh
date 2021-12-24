# Python |连续子集最小值

> 原文:[https://www . geeksforgeeks . org/python-连续-子集-最小值/](https://www.geeksforgeeks.org/python-consecutive-subsets-minimum/)

编程领域的一些经典问题来自不同的类别，其中之一就是求子集的最小值。当我们需要累加最小值并存储连续的组最小值时，这个特殊的问题也很常见。让我们用 python 语言尝试不同的方法来解决这个问题。

**方法#1:使用列表理解+ `min()`**
可以使用列表理解来执行这个特定的任务以过滤掉连续的组，并且可以使用 min 函数来获得被过滤的解的最小值。

```
# Python3 code to demonstrate
# Consecutive Subsets Minimum
# using list comprehension + min()

# initializing list
test_list = [4, 7, 8, 10, 12, 15, 13, 17, 14]

# printing original list 
print("The original list : " + str(test_list))

# using list comprehension + min()
# Consecutive Subsets Minimum
res = [ min(test_list[x : x + 3]) for x in range(0, len(test_list), 3)]

# printing result
print("The grouped minimum list is : " + str(res))
```

**Output :**

```
The original list : [4, 7, 8, 10, 12, 15, 13, 17, 14]
The grouped minimum list is : [4, 10, 13]

```