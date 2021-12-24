# Python |列表中重复的元素索引

> 原文:[https://www . geesforgeks . org/python-重复元素-列表中的索引/](https://www.geeksforgeeks.org/python-duplicate-element-indices-in-list/)

在使用 Python 列表时，有时，我们需要检查重复项，有时可能还需要跟踪它们的索引。这种应用可以出现在日常编程中。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用 loop + `set()`**
这个任务可以使用以上功能的组合来解决。在这种情况下，我们只需插入集合中的所有元素，然后比较每个元素在实际列表中的存在性。如果这是第二次或更多次出现，则在结果列表中添加索引。

```
# Python3 code to demonstrate working of
# Duplicate element indices in list
# Using set() + loop

# initializing list
test_list = [1, 4, 5, 5, 5, 9, 1]

# printing original list
print("The original list is : " + str(test_list))

# Duplicate element indices in list
# Using set() + loop
oc_set = set()
res = []
for idx, val in enumerate(test_list):
    if val not in oc_set:
        oc_set.add(val)         
    else:
        res.append(idx)     

# printing result
print("The list of duplicate elements is :  " + str(res))
```

**Output :**

```
The original list is : [1, 4, 5, 5, 5, 9, 1]
The list of duplicate elements is :  [3, 4, 6]

```