# Python | K 除法分组

> 原文:[https://www.geeksforgeeks.org/python-k-division-grouping/](https://www.geeksforgeeks.org/python-k-division-grouping/)

有时，我们遇到一个问题，需要处理元素的分组。使用数据库时，这些分组相对容易一些，但是使用语言时，这可能会很棘手。让我们讨论在 Python 中由 k 执行分组的某些方法。

**方法#1:使用循环**
这是执行这个特殊任务的蛮力方法。在这种情况下，我们使用循环来获得每个数字的 K 位置，并将该数字添加到指定列表中。

```py
# Python3 code to demonstrate
# K Division Grouping
# using loops

# initializing list
test_list = [3, 12, 13, 22, 25, 30]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 7

# using loops
# K Division Grouping
res = []
dec = -1
for num in sorted(test_list):
    while num // K != dec:
        res.append([])
        dec += 1
    res[-1].append(num)

# print result
print("The list after grouping by K is : " + str(res))
```

**Output :**

```py
The original list : [3, 12, 13, 22, 25, 30]
The list after grouping by K is : [[3], [12, 13], [], [22, 25], [30]]

```