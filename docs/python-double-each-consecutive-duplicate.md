# Python–将每个连续副本加倍

> 原文:[https://www . geesforgeks . org/python-双-每-连续-重复/](https://www.geeksforgeeks.org/python-double-each-consecutive-duplicate/)

有时，在处理数据时，我们可能会遇到这样的问题，即我们需要对重复的每个连续出现的元素执行 double。这是一个非常具体的问题，但解决这个问题会非常方便。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是用蛮力的方式来执行这个任务。在这种情况下，我们迭代每个元素，当我们发现重复时，我们存储在字典中，并随后执行它的加倍。

```
# Python3 code to demonstrate 
# Double each consecutive duplicate
# using loop

# Initializing list
test_list = [1, 2, 4, 2, 4, 1, 2]

# printing original list
print("The original list is : " + str(test_list))

# Double each consecutive duplicate
# using loop
temp = {}
res = []
for ele in test_list:
    temp[ele] = temp1 = temp.get(ele, 0) + ele
    res.append(temp1)

# printing result 
print ("The list after manipulation is : " + str(res))
```

**Output :**

```
The original list is : [1, 2, 4, 2, 4, 1, 2]
The list after manipulation is : [1, 2, 4, 4, 8, 2, 6]

```