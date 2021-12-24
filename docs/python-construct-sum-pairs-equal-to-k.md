# Python–构造等于 K 的和对

> 原文:[https://www . geesforgeks . org/python-construct-sum-pairs-equal-to-k/](https://www.geeksforgeeks.org/python-construct-sum-pairs-equal-to-k/)

有时，在使用 Python 列表时，我们可能会遇到需要提取总和等于 k 的对的问题。这种问题很常见，可以应用于诸如 web 开发和日常编程等领域。让我们讨论执行这项任务的某些方法。

```
Input : 
test_list = [1, 9, 5, 5, 7]
K = 10
Output : [(1, 9), (5, 5)]

Input : 
test_list = [1, 9, 7, 8, 3]
K = 12
Output : [(9, 3)]

```

**方法#1:使用列表理解+ `sum()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 sum()执行寻找等于 K 的求和的任务，列表理解用于逻辑和配对构建。

```
# Python3 code to demonstrate working of 
# Construct Sum pairs equal to K
# Using list comprehension + sum()

# initializing list
test_list = [3, 4, 0, 5, 2]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 7

# Construct Sum pairs equal to K
# Using list comprehension + sum()
res = [(test_list[idx], test_list[j]) for idx in range(len(test_list))
                               for j in range(idx + 1, len(test_list))
                          if sum((test_list[idx], test_list[j])) == K]

# printing result 
print("The paired tuples equal to K  : " + str(res)) 
```

**Output :**

```
The original list is : [3, 4, 0, 5, 2]
The paired tuples equal to K  : [(3, 4), (5, 2)]

```