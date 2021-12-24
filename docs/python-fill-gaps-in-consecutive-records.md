# Python–填充连续记录中的空白

> 原文:[https://www . geeksforgeeks . org/python-填补连续记录中的空白/](https://www.geeksforgeeks.org/python-fill-gaps-in-consecutive-records/)

有时，在使用 Python 记录时，我们可能会遇到一个问题，其中我们有连续的记录，但有几个丢失了，需要用任何常数 k 来填充。这种问题在 web 开发等领域可能会有应用。让我们讨论一下执行这项任务的某些方法。

> **输入** :
> 测试 _ 列表= [(1，4)，(9，11)]
> K =无
> **输出** : [(1，4)，(2，无)，(3，无)，(4，无)，(5，无)，(6，无)，(7，无)，(8，无)，(9，11)]
> 
> **输入** :
> 测试 _ 列表= [(1，4)，(2，11)]
> K =无
> **输出** : [(1，4)，(2，11)]

**方法#1:使用循环**
这是解决这个问题的一种方法。在这种情况下，我们在每次迭代中检查元素是否存在，如果不存在，则用所需的值填充它，如果存在，则保留原始值。

```py
# Python3 code to demonstrate working of 
# Fill gaps in consecutive Records
# Using loop

# initializing list
test_list = [(1, 4), (3, 5), (4, 6), (7, 8), (9, 11)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K value
K = "New"

# Fill gaps in consecutive Records
# Using loop
res = []
cnt = 0
for i, j in test_list:
    if i - cnt > 1:
        for k in range(cnt + 1, i):
            res.append((k, K))
    res.append((i, j))
    cnt = i

# printing result 
print("The list after filling gaps : " + str(res)) 
```

**Output :**

> 原列表为:[(1，4)，(3，5)，(4，6)，(7，8)，(9，11)]
> 填空后的列表:[(1，4)，(2，'新')，(3，5)，(4，6)，(5，'新')，(6，'新')，(7，8)，(8，'新')，(9，11)]

**方法二:使用`min() + max() + dict()` +列表理解**
这是解决这个问题的又一种方法。在这种情况下，我们使用 min()和 max()检查范围，并使用字典作为获取需要填写的值的容器。

```py
# Python3 code to demonstrate working of 
# Fill gaps in consecutive Records
# Using min() + max() + dict() + list comprehension

# initializing list
test_list = [(1, 4), (3, 5), (4, 6), (7, 8), (9, 11)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K value
K = "New"

# Fill gaps in consecutive Records
# Using min() + max() + dict() + list comprehension
test_list = dict(test_list)
mini, maxi = min(test_list), max(test_list)
res = [(idx, test_list.get(idx)) for idx in range(mini, maxi + 1)]

# printing result 
print("The list after filling gaps : " + str(res)) 
```

**Output :**

> 原列表为:[(1，4)，(3，5)，(4，6)，(7，8)，(9，11)]
> 填空后的列表:[(1，4)，(2，'新')，(3，5)，(4，6)，(5，'新')，(6，'新')，(7，8)，(8，'新')，(9，11)]