# Python–连续缺失元素总和

> 原文:[https://www . geesforgeks . org/python-continuous-missing-elements-sum/](https://www.geeksforgeeks.org/python-consecutive-missing-elements-sum/)

有时，我们可以将范围内的元素作为输入，但在其他连续的范围内，有些值会丢失。我们可能有一个用例，其中我们需要得到所有缺失元素的总和。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `sum()`**
我们可以使用范围函数执行查找缺失元素的任务，以获得最大的元素填充，如果有缺失，则插入元素。求和使用 sum()执行。

```
# Python3 code to demonstrate
# Consecutive Missing elements Sum
# using list comprehension + sum()

# initializing list
test_list = [3, 5, 6, 8, 10]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + sum()
# Consecutive Missing elements Sum
res = sum([ele for ele in range(max(test_list) + 1) if ele not in test_list])

# print result
print("The sum of missing elements : " + str(res))
```

**Output :**

```
The original list : [3, 5, 6, 8, 10]
The sum of missing elements : 23

```