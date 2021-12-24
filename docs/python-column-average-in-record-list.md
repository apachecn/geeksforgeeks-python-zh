# Python |记录列表中的列平均值

> 原文:[https://www . geesforgeks . org/python-column-in-average-in-record-list/](https://www.geeksforgeeks.org/python-column-average-in-record-list/)

有时，我们收到的数据是元组的形式，包含来自不同来源的数据，我们通常会有一个用例，在这个用例中，我们需要处理元组的每个索引的平均值，以进行累积。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解**
这是执行这个特定任务最天真的方法，在这个方法中我们计算元组的所有可能索引的每个索引的平均值。

```py
# Python3 code to demonstrate 
# Column Average in Record List
# using list comprehension

# initializing list 
test_list = [(1, 6), (3, 4), (5, 8)]

# printing original list 
print ("The original list is : " + str(test_list))

# Column Average in Record List
# using list comprehension
temp = sum(i[0] for i in test_list), sum(i[1] for i in test_list)
res = []
for ele in temp:
    res.append(ele / len(test_list))

# printing summation
print ("The position Average of tuples : " + str(res))
```

**Output :**

```py
The original list is : [(1, 6), (3, 4), (5, 8)]
The position Average of tuples : [3.0, 6.0]

```