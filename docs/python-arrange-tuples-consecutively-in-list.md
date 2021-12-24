# Python |在列表中连续排列元组

> 原文:[https://www . geeksforgeeks . org/python-array-元组-连续在列表中/](https://www.geeksforgeeks.org/python-arrange-tuples-consecutively-in-list/)

有时，在使用元组列表时，我们可能需要这样一种情况，即我们要求一个元组从上一个元组的末尾开始，即每个元组的元素 0 应该等于元组列表中元组的结束元素。这种类型的问题和排序在竞争性编程中很有用。让我们讨论一下解决这个问题的方法。

**方法:使用 loop + `dict()`**
通过将元组容器列表转换为字典，然后很容易访问一个键的值，并相应地排列它们，以一个元组元素以另一个元素的结尾开始的方式进行排序，可以很容易地解决这个任务。

```
# Python3 code to demonstrate working of
# Arranging Tuples consecutively in list
# using loop + dict()

# initialize list
test_list = [(5, 6), (11, 8), (6, 11), (8, 9) ]

# printing original list
print("The original list is : " + str(test_list))

# Arranging Tuples consecutively in list
# using loop + dict()
temp = dict(test_list)  
ele = test_list[0][0]  
res = [] 
for _ in range(len(test_list)):
    res.append((ele, temp[ele]))
    ele = temp[ele]

# printing result
print("The arranged list is : " + str(res))
```

**Output :**

```
The original list is : [(5, 6), (11, 8), (6, 11), (8, 9)]
The arranged list is : [(5, 6), (6, 11), (11, 8), (8, 9)]

```