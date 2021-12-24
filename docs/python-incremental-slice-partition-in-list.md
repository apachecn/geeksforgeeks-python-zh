# Python |列表中的增量切片分区

> 原文:[https://www . geesforgeks . org/python-增量-切片-列表中的分区/](https://www.geeksforgeeks.org/python-incremental-slice-partition-in-list/)

有时，在处理列表时，我们会遇到一个问题，即我们需要对列表进行增量切片，也就是说，对于每个切片，元素的数量增加 1。这在竞争性编程中有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方法。我们只是手动计数，并随着切片和字典键创建的每次迭代增加计数器。

```
# Python3 code to demonstrate working of
# Incremental slice partition in list
# Using loop

# initializing list
test_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# printing original list
print("The original list is : " + str(test_list))

# Incremental slice partition in list
# Using loop
res = {}
N = 1
strt = 0
while strt < len(test_list):
    res[N] = test_list[strt : strt + N]
    strt += N
    N += 1

# printing result 
print("The partitioned dictionary from list is : " + str(res))
```

**Output :**

> 原始列表为:[1，2，3，4，5，6，7，8，9，10]
> 列表中的分区字典为:{1: [1]，2: [2，3]，3: [4，5，6]，4: [7，8，9，10]}