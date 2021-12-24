# Python |列表元素的频率分组

> 原文:[https://www . geesforgeks . org/python-frequency-group-of-list-elements/](https://www.geeksforgeeks.org/python-frequency-grouping-of-list-elements/)

有时，在处理列表时，我们会遇到一个问题，即我们需要以元组列表的形式对元素及其频率进行分组。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是一个蛮力方法来执行这个特定的任务。在这种情况下，我们迭代每个元素，在其他列表中检查它的存在，如果是，那么增加它的计数并放入元组。

```
# Python3 code to demonstrate working of
# Frequency grouping of list elements
# using loop

# initialize list 
test_list = [1, 3, 3, 1, 4, 4]

# printing original list 
print("The original list : " + str(test_list))

# Frequency grouping of list elements
# using loop
res = []
temp = dict()
for ele in test_list:
    if ele in temp:
        temp[ele] = temp[ele] + 1 
    else : 
        temp[ele] = 1
for key in temp:
    res.append((key, temp[key]))

# printing result
print("Frequency of list elements : " + str(res))
```

**Output :**

```
The original list : [1, 3, 3, 1, 4, 4]
Frequency of list elements : [(1, 2), (3, 2), (4, 2)]

```