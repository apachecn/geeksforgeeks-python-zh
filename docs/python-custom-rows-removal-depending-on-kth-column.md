# Python–根据第 k 列

自定义行删除

> 原文:[https://www . geesforgeks . org/python-custom-row-remove-on-kth-column/](https://www.geeksforgeeks.org/python-custom-rows-removal-depending-on-kth-column/)

有时，在使用 Python Matrix 时，我们会遇到一个问题，即需要根据参数列表中的第 Kth Column 元素从 Matrix 中移除元素。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是一种可以执行该任务的暴力方式。在这种情况下，我们迭代矩阵的行，从列表中检查 Kth 列匹配值，并从新列表中排除。

```
# Python3 code to demonstrate 
# Custom Rows Removal depending on Kth Column
# using loop

# Initializing lists
test_list1 = [[3, 4, 5], [2, 6, 8], [1, 10, 2], [5, 7, 9], [10, 1, 2]]
test_list2 = [12, 4, 6]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Initializing K 
K = 1

# Custom Rows Removal depending on Kth Column
# using loop
res = []
for ele in test_list1:
  if ele[K] not in test_list2:
    res.append(ele)

# printing result 
print ("The matrix after rows removal is : " + str(res))
```

**Output :**

> 原始列表 1 为:[[3，4，5]，[2，6，8]，[1，10，2]，[5，7，9]，[10，1，2]]
> 原始列表 2 为:[12，4，6]
> 行删除后的矩阵为:[[1，10，2]，[5，7，9]，[10，1，2]]