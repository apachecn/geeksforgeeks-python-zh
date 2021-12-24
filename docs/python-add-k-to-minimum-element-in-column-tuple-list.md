# Python–将 K 添加到列元组列表中的最小元素

> 原文:[https://www . geesforgeks . org/python-add-k-to-minimum-in-column-tuple-list/](https://www.geeksforgeeks.org/python-add-k-to-minimum-element-in-column-tuple-list/)

有时，在处理元组记录时，我们可能会遇到一个问题，即我们需要执行向元组列表的每一列的 max/ min 元素添加特定元素的任务。这类问题在 web 开发领域会有应用。让我们讨论一下执行这项任务的特定方式。

> **输入** : test_list = [(4，5)，(3，2)，(2，2)，(4，6)，(3，2)，(4，5)]，K = 2
> **输出** : [(4，5)，(3，4)，(4，4)，(4，6)，(3，4)，(4，5)]
> 
> **输入** : test_list = [(4，5)，(3，2)，(2，2)，(4，6)，(3，2)，(4，5)]，K = 3
> **输出** : [(4，5)，(3，5)，(5，5)，(4，6)，(3，5)，(4，5)，(4，5)

**方法:使用 `min()` +循环**
以上功能的组合可以解决这个问题。在本例中，我们使用 min()为每列提取 min，并使用循环编译的逻辑添加 K。

```py
# Python3 code to demonstrate working of 
# Add K to Minimum element in Column Tuple List
# Using min() + loop

# initializing lists
test_list = [(4, 5), (3, 2), (2, 2), (4, 6), (3, 2), (4, 5)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 5

# Add K to Minimum element in Column Tuple List
# Using min() + loop
a_min = min(a for a, b in test_list)
b_min = min(b for a, b in test_list)
res = []

for a, b in test_list:
    if a == a_min and b == b_min:
        res.append((a + K, b + K))
    elif a == a_min :
        res.append((a + K, b))
    elif b == b_min:
        res.append((a, b + K))
    else :
        res.append((a, b))

# printing result 
print("Tuple after modification : " + str(res))
```

**Output :**

```py
The original list is : [(4, 5), (3, 2), (2, 2), (4, 6), (3, 2), (4, 5)]
Tuple after modification : [(4, 5), (3, 7), (7, 7), (4, 6), (3, 7), (4, 5)]

```