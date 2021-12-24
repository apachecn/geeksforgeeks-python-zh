# Python |查找列表中缺失的元素

> 原文:[https://www . geesforgeks . org/python-find-missing-elements-in-list/](https://www.geeksforgeeks.org/python-find-missing-elements-in-list/)

有时，我们可以将范围内的元素作为输入，但在其他连续的范围内，有些值会丢失。我们可能有一个用例，在这个用例中，我们需要获取所有缺失的元素。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解**
我们可以使用 range 函数执行查找缺失元素的任务，以获得最大的元素填充，如果有缺失，则插入元素。

```py
# Python3 code to demonstrate
# Finding missing elements in List
# using list comprehension

# initializing list
test_list = [3, 5, 6, 8, 10]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension
# Finding missing elements in List
res = [ele for ele in range(max(test_list)+1) if ele not in test_list]

# print result
print("The list of missing elements : " + str(res))
```

**Output :**

```py
The original list : [3, 5, 6, 8, 10]
The list of missing elements : [0, 1, 2, 4, 7, 9]

```