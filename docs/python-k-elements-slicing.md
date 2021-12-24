# Python | K 元素切片

> 原文:[https://www.geeksforgeeks.org/python-k-elements-slicing/](https://www.geeksforgeeks.org/python-k-elements-slicing/)

我们经常会遇到需要提取列表初始 K 元素的情况。当我们需要优化内存时，就会出现这个特殊的问题。这在日常编程中有其应用，有时我们需要得到所有相似大小的列表。让我们讨论执行这项任务的某些方法。

**方法#1:使用`len()` +列表切片**
列表切片可以执行这个特殊的任务，在这个任务中，我们只需将列表中的前 K 个元素切片，从而移除剩余的元素，释放内存。

```py
# Python code to demonstrate 
# K elements Slicing
# using len() + list slicing

# initializing list 
test_list = [1, 4, 6, 3, 5, 8]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K 
K = 4

# using len() + list slicing
# K elements Slicing
res = test_list[: K]

# printing result 
print ("The K sliced List : " + str(res))
```

**Output :**

```py
The original list is : [1, 4, 6, 3, 5, 8]
The K sliced List : [1, 4, 6, 3]

```