# Python–检查元组列表是否全部为 K

> 原文:[https://www . geesforgeks . org/python-check-if-tuple-list-has-all-k/](https://www.geeksforgeeks.org/python-check-if-tuple-list-has-all-k/)

有时候，在处理 Python 记录时，我们会遇到一个问题，我们需要测试元组列表的元组中的所有元素是否都是 k，这个问题在机器学习和 Web 开发等许多数据领域都有应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(4，4，4，4)]，K = 4
> **输出**:真
> 
> **输入** : test_list = [(7)、(5)、(5)、(5)、(5)、]，K = 5
> **输出** : False

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们使用循环来迭代元组中的每个值，并测试它的 K，如果我们发现任何元素是非 K，则返回 False。

```py
# Python3 code to demonstrate working of 
# Check if tuple list has all K
# Using loop

# initializing list
test_list = [(4, 4), (4, 4, 4), (4, 4), (4, 4, 4, 4), (4, )]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 4

# Check if tuple list has all K
# Using loop
res = True
for tup in test_list:                  
    for ele in tup:
        if ele != K:
            res = False

# printing result 
print("Are all elements K ? : " + str(res)) 
```

**Output :**

```py
The original list is : [(4, 4), (4, 4, 4), (4, 4), (4, 4, 4, 4), (4, )]
Are all elements K ? : True

```

**方法 2:使用`all() + any()`**
这是回答这个问题的又一种方式。在本例中，我们使用 all()检查所有元素是否为 K，并使用 outer any()检查它们中是否有任何元素不遵循此行为。

```py
# Python3 code to demonstrate working of 
# Check if tuple list has all K
# Using all() + any()

# initializing list
test_list = [(4, 4), (4, 4, 4), (4, 4), (4, 4, 4, 4), (4, )]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 4

# Check if tuple list has all K
# Using all() + any()
res = any(all(val == K for val in tup) for tup in test_list)

# printing result 
print("Are all elements K ? : " + str(res)) 
```

**Output :**

```py
The original list is : [(4, 4), (4, 4, 4), (4, 4), (4, 4, 4, 4), (4, )]
Are all elements K ? : True

```