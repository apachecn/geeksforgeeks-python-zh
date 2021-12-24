# Python–将列表转换为单字典键值列表

> 原文:[https://www . geesforgeks . org/python-convert-list-to-single-dictionary-key-value-list/](https://www.geeksforgeeks.org/python-convert-list-to-single-dictionary-key-value-list/)

有时，在使用 Python 列表时，我们会遇到一个问题，我们需要将列表转换为字典，该字典有一个键、列表的 Kth 元素以及其他作为其列表值的元素。这种问题可以在数据领域得到应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [6，5，3，2]，K = 1
> **输出** : {5 : [6，3，2]}
> 
> **输入** : test_list = [6，5，3，2]，K = 2
> **输出** : {5 : [6，5，2]}

**方法#1:使用循环**
这是执行该任务的方法之一。在这种情况下，我们首先创建一个关键字，然后添加除 K 索引之外的值来创建字典列表。

```
# Python3 code to demonstrate working of 
# Convert list to Single Dictionary Key Value list
# Using loop

# initializing list
test_list = [5, 6, 3, 8, 9] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

# Convert list to Single Dictionary Key Value list
# Using loop
res = {test_list[K] : []}
for idx in range(len(test_list)):
    if idx != K:
        res[test_list[K]].append(test_list[idx])

# printing result 
print("Records after conversion : " + str(res))
```

**Output :**

```
The original list is : [5, 6, 3, 8, 9]
Records after conversion : {8: [5, 6, 3, 9]}

```

**方法#2:使用列表切片**
这是另一个可以执行该任务的线性。在这种情况下，我们在 Kth 索引上切掉列表，并在字典中赋值。

```
# Python3 code to demonstrate working of 
# Convert list to Single Dictionary Key Value list
# Using loop

# initializing list
test_list = [5, 6, 3, 8, 9] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

# Convert list to Single Dictionary Key Value list
# Using loop
res = {test_list[K] : test_list[:K] + test_list[K + 1:]}

# printing result 
print("Records after conversion : " + str(res))
```

**Output :**

```
The original list is : [5, 6, 3, 8, 9]
Records after conversion : {8: [5, 6, 3, 9]}

```