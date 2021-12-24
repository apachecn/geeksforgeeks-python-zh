# Python |查找给定列表中无值的索引

> 原文:[https://www . geesforgeks . org/python-find-indexes-with-none-values-in-给定列表/](https://www.geeksforgeeks.org/python-find-indices-with-none-values-in-given-list/)

在数据科学领域工作的时候，很多时候我们需要得到所有*无*的指标列表，这样就可以很容易的将它们前置。这是一个很受欢迎的问题，解决它的方法很方便。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `range()`**
在该方法中，我们只需使用 range 函数检查每个索引，如果发现该索引为 None，则存储该索引。

```
# Python3 code to demonstrate
# finding None indices in list 
# using list comprehension + enumerate

# initializing list 
test_list = [1, None, 4, None, None, 5]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + enumerate
# finding None indices in list 
res = [i for i in range(len(test_list)) if test_list[i] == None]

# print result
print("The None indices list is : " + str(res))
```

**Output :**

```
The original list : [1, None, 4, None, None, 5]
The None indices list is : [1, 3, 4]

```