# Python–列表中大气 K 元素的索引

> 原文:[https://www . geesforgeks . org/python-indexs-of-Atmos-k-elements-in-list/](https://www.geeksforgeeks.org/python-indices-of-atmost-k-elements-in-list/)

很多时候，我们可能会遇到这样的问题:我们需要找到指数，而不是实际数字，而且更多时候，结果是有条件的。首先想到的方法可以是一个简单的索引函数，并获得小于或等于特定数字的索引，但这种方法在重复数字的情况下会失败。让我们讨论一下成功解决这个问题的某些方法。

**方法#1:使用循环**
这个问题可以很容易地通过使用带有强力方法的循环来解决，在这种方法中，我们可以在迭代时检查索引，并在前进时将其附加到新列表中。

```
# Python3 code to demonstrate
# Atmost K element indices
# using loop

# initializing list 
test_list = [12, 11, 7, 15, 8, 18]

# printing original list
print("The original list : " + str(test_list))

# using loop
# Atmost K element indices
res = []
for idx in range(0, len(test_list)) :
    if test_list[idx] <= 11:
        res.append(idx)

# print result
print("The list of indices at most 11 : " + str(res))
```

**Output :**

```
The original list : [12, 11, 7, 15, 8, 18]
The list of indices at most 11 : [1, 2, 4]

```