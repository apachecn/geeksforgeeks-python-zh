# Python |从列表中获取重复元组

> 原文:[https://www . geesforgeks . org/python-get-replicate-元组-from-list/](https://www.geeksforgeeks.org/python-get-duplicate-tuples-from-list/)

有时，在处理记录时，我们可能会遇到提取那些出现不止一次的记录的问题。这种应用可以出现在 web 开发领域。让我们讨论执行这项任务的某些方法。

**方法一:使用列表理解+ `set() + count()`**
可以应用的初始方法是我们可以迭代每个元组，并使用`count()`检查它在列表中的计数，如果大于 1，我们可以添加到列表中。要删除多个添加，我们可以使用`set()`将结果转换为集合。

```
# Python3 code to demonstrate working of
# Get duplicate tuples from list
# Using list comprehension + set() + count()

# initialize list
test_list = [(3, 4), (4, 5), (3, 4), 
             (3, 4), (4, 5), (6, 7)]

# printing original list 
print("The original list : " + str(test_list))

# Get duplicate tuples from list
# Using list comprehension + set() + count()
res = list(set([ele for ele in test_list
            if test_list.count(ele) > 1]))

# printing result
print("All the duplicates from list are : " + str(res))
```

**Output :**

```
The original list : [(3, 4), (4, 5), (3, 4), (3, 4), (4, 5), (6, 7)]
All the duplicates from list are : [(4, 5), (3, 4)]

```