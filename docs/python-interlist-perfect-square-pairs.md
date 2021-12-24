# Python–Interlist 完美方块对

> 原文:[https://www . geesforgeks . org/python-interlist-perfect-square-pairs/](https://www.geeksforgeeks.org/python-interlist-perfect-square-pairs/)

有时，在数学领域工作时，我们会遇到一个问题，我们需要检查来自不同列表的元素的乘积是否能得到完美的正方形。这可以应用于许多领域，包括数学和网络开发。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这个任务可以使用循环来执行。这是我们执行这项任务的强力方式。在这种情况下，我们将每个元素与其他元素相乘，并检查它是否是完美的正方形。

```py
# Python3 code to demonstrate 
# Interlist Perfect Square Pairs
# using loop

# Initializing lists
test_list1 = [4, 5, 6, 7, 3, 4]
test_list2 = [6, 4, 2, 8, 9, 4]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Flatten List to individual elements
# using chain() + isinstance()
res = []
idx = 0
while(idx < len(test_list1)):
    j = 0
    while(j < len(test_list2)):
        sub = test_list1[idx] * test_list2[j]
        n = sub**0.5
        temp = int(n)
        if n == temp:
            res.append((test_list1[idx], test_list2[j]))
        j = j + 1
    idx = idx + 1

# printing result 
print ("The perfect square pairs are : " + str(res))
```

**Output :**

> 原列表 1 为:【4，5，6，7，3，4】
> 原列表 2 为:【6，4，2，8，9，4】
> 完美的正方形对为:[(4，4)，(4，9)，(4，4)，(6，6)，(4，4)，(4)，(4，9)，(4，4，4)]