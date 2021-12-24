# Python–来自两个列表的 K 求和

> 原文:[https://www . geesforgeks . org/python-k-summary-from-two-list/](https://www.geeksforgeeks.org/python-k-summation-from-two-lists/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们需要找到从两个不同列表中提取元素的列表的总和。这种应用程序可以出现在不同的领域，例如 web 开发。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这个任务可以通过蛮力的方式使用循环来完成。我们对每个列表运行一个嵌套循环，当我们找到匹配时，我们用该对更新结果列表。

```py
# Python3 code to demonstrate 
# K Summation from Two lists
# using loop

# Initializing lists
test_list1 = [3, 2, 5]
test_list2 = [4, 3, 6, 8, 7]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Initializing K 
K = 9

# K Summation from Two lists
# using loop
res = []
for idx in test_list1:
    val_req = K - idx
    for j in test_list2:
        if j == val_req:
            x, y = j, idx
            res.append((x, y))

# printing result 
print ("Summation pairs among lists : " + str(res))
```

**Output :**

```py
The original list 1 is : [3, 2, 5]
The original list 2 is : [4, 3, 6, 8, 7]
Summation pairs among lists : [(6, 3), (7, 2), (4, 5)]

```