# Python | K 分割索引列表

> 原文:[https://www . geesforgeks . org/python-k-divided-indexs-list/](https://www.geeksforgeeks.org/python-k-divided-indices-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，我们希望找到模 K 元素。这项工作可以在许多领域进行，例如网页开发和使用数据库。我们有时可能需要找到它们的索引。让我们讨论寻找模 K 元素索引的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方法。在这种情况下，我们检查列表中的% K 元素，并相应地附加其索引。

```py
# Python3 code to demonstrate working of 
# K Divident Indices List
# using loop 

# initialize list 
test_list = [5, 6, 10, 4, 7, 1, 19] 

# printing original list 
print("The original list is : " + str(test_list)) 

# initializing K 
K = 5

# K Divident Indices List
# using loop 
res = [] 
for idx, ele in enumerate(test_list): 
    if ele % K == 0: 
        res.append(idx) 

# printing result 
print("Indices list modulo K elements is : " + str(res)) 
```

**Output :**

```py
The original list is : [5, 6, 10, 4, 7, 1, 19]
Indices list modulo K elements is : [0, 2]

```