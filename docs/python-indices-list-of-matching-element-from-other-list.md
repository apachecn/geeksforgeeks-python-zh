# Python |其他列表中匹配元素的索引列表

> 原文:[https://www . geesforgeks . org/python-indexs-匹配元素列表-来自其他列表/](https://www.geeksforgeeks.org/python-indices-list-of-matching-element-from-other-list/)

有时候，在使用 Python 列表时，我们会遇到一个问题，那就是我们必须在列表中搜索一个元素。但是这可以扩展到一个列表，需要找到其他列表中元素出现的确切位置。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `count()`**
这是执行这个任务的蛮法。在这种情况下，我们可以计算一个元素在其他列表中的出现次数，如果我们找到它，那么我们就把它的索引添加到结果列表中。

```
# Python3 code to demonstrate working of
# Indices list of matching element from other list
# Using loop + count()

# initializing lists
test_list1 = [5, 7, 8, 9, 10, 11]
test_list2 = [8, 10, 11]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Indices list of matching element from other list
# Using loop + count()
res = []
i = 0
while (i < len(test_list1)):
    if (test_list2.count(test_list1[i]) > 0):
        res.append(i)
    i += 1

# printing result 
print("The matching element Indices list : " + str(res))
```

**Output :**

```
The original list 1 is : [5, 7, 8, 9, 10, 11]
The original list 2 is : [8, 10, 11]
The matching element Indices list : [2, 4, 5]

```