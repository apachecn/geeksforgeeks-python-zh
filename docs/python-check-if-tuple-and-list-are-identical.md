# Python |检查元组和列表是否相同

> 原文:[https://www . geesforgeks . org/python-检查元组和列表是否相同/](https://www.geeksforgeeks.org/python-check-if-tuple-and-list-are-identical/)

有时在 Python 中处理不同的数据时，我们可能会遇到将数据放在不同容器中的问题。在这种情况下，可能需要测试跨容器的数据是否相同。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是执行这个特殊任务的蛮力方法。在这种情况下，我们只是迭代列表和元组来测试每个索引处的元素是否相似。

```py
# Python3 code to demonstrate working of
# Check if tuple and list are identical
# Using loop

# Initializing list and tuple
test_list = ['gfg', 'is', 'best']
test_tup = ('gfg', 'is', 'best')

# printing original list and tuple 
print("The original list is : " + str(test_list))
print("The original tuple is : " + str(test_tup))

# Check if tuple and list are identical
# Using loop
res = True
for i in range(0, len(test_list)):
    if(test_list[i] != test_tup[i]):
        res = False
        break

# printing result
print("Are tuple and list identical ? : " + str(res))
```

**Output :**

```py
The original list is : ['gfg', 'is', 'best']
The original tuple is : ('gfg', 'is', 'best')
Are tuple and list identical ? : True

```