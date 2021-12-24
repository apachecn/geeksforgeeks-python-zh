# Python |从列表中提取唯一元组，顺序无关

> 原文:[https://www . geesforgeks . org/python-extract-unique-tuples-from-list-order-无关/](https://www.geeksforgeeks.org/python-extract-unique-tuples-from-list-order-irrespective/)

有时，在处理数据时，我们可能会遇到一个问题，需要检查类似的记录并消除它们。当元素被排序时，这种情况之前已经讨论过了。但是有时，我们可能不得不忽略这个顺序，并且在类似的元素出现的情况下必须删除。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `set()`**
可以组合上述功能来执行该特定任务。在这种情况下，我们检查每一对，并添加到一个集合中作为参考，以检查它以前是否存在，并添加它是否是新的。

```py
# Python3 code to demonstrate working of
# Extract unique tuples from list(Order Irrespective)
# using list comprehension + set()

# initialize tuples list 
test_list = [(1, 3), (4, 5), (3, 1), (1, 10), (5, 4)]

# printing original list 
print("The original list : " + str(test_list))

# Extract unique tuples from list(Order Irrespective)
# using list comprehension + set()
res = set() 
temp = [res.add((a, b)) for (a, b) in test_list 
              if (a, b) and (b, a) not in res]

# printing result
print("The list after duplicated removal : " + str(list(res)))
```

**Output :**

```py
The original list : [(1, 3), (4, 5), (3, 1), (1, 10), (5, 4)]
The list after duplicated removal : [(4, 5), (1, 3), (1, 10)]

```