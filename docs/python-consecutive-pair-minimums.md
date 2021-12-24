# Python |连续对最小值

> 原文:[https://www . geesforgeks . org/python-continuous-pair-minimums/](https://www.geeksforgeeks.org/python-consecutive-pair-minimums/)

有时，在使用 Python 列表时，可能会遇到一个问题，即需要找到并执行最小列表对形式。这对于 web 开发和日常编程中较大问题的子问题解决方案非常有用。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环**
这是执行这个特殊任务的蛮力方法。在这种情况下，我们只是以跳过的方式迭代列表直到最后一个元素，以迭代的方式获得其他列表中的所有最小对。

```py
# Python3 code to demonstrate working of
# Consecutive Pair Minimums
# Using loop

# initializing list
test_list = [4, 5, 8, 9, 10, 17]

# printing list
print("The original list : " + str(test_list))

# Consecutive Pair Minimums
# Using loop
res = []
for ele in range(0, len(test_list), 2):
    res.append(min(test_list[ele], test_list[ele + 1]))

# Printing result
print("Pair minimum of list : " + str(res))
```

**Output :**

```py
The original list : [4, 5, 8, 9, 10, 17]
Pair minimum of list : [4, 8, 10]

```