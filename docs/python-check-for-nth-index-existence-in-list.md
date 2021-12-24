# Python |检查列表中是否存在第 n 个索引

> 原文:[https://www . geesforgeks . org/python-第 n 次检查-索引-列表中的存在/](https://www.geeksforgeeks.org/python-check-for-nth-index-existence-in-list/)

有时，在处理列表时，我们会遇到一个问题，即我们需要在索引处插入一个特定的元素。但是，在此之前，必须知道特定的索引是否是列表的一部分。让我们来讨论一下可以无错执行这项任务的某些人手不足的情况。

**方法一:使用`len()`**
使用`len()`查找列表长度，可以轻松执行此任务。我们可以检查所需的索引是否小于长度，这将证明它的存在。

```
# Python3 code to demonstrate working of
# Check for Nth index existence in list
# Using len()

# initializing list
test_list = [4, 5, 6, 7, 10]

# printing original list
print("The original list is : " + str(test_list))

# initializing N 
N = 6

# Check for Nth index existence in list
# Using len()
res = len(test_list) >= N

# printing result 
print("Is Nth index available? : " + str(res))
```

**Output :**

```
The original list is : [4, 5, 6, 7, 10]
Is Nth index available? : False

```