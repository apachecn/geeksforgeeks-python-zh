# Python–列表中最接近的和对

> 原文:[https://www . geeksforgeeks . org/python-最接近列表中对和/](https://www.geeksforgeeks.org/python-closest-sum-pair-in-list/)

有时，我们希望得到特定元素的总和。但是在我们找不到的情况下，我们的目标变成了找到最接近的那个。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用词典理解+ `max()`**
上述功能的组合可用于执行该任务。在这种情况下，我们执行字典理解中的逻辑部分，并使用 max()提取最接近的对。应该对列表进行排序以执行此方法。

```
# Python3 code to demonstrate 
# Closest Sum Pair in List
# using dictionary comprehension + max()

# Initializing list
test_list = [7, 8, 10, 3, 18, 1]

# printing original list
print("The original list is : " + str(test_list))

# Initializing K 
K = 12

# Closest Sum Pair in List
# using dictionary comprehension + max()
test_list.sort()
res = { i + j :(i, j) for i in test_list for j in test_list if i != j and i + j < K}
res = max(res)

# printing result 
print ("The closest sum pair is : " + str(res))
```

**Output :**

```
The original list is : [7, 8, 10, 3, 18, 1]
The closest sum pair is : 11

```