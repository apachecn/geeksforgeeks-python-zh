# Python–列表的分块交错

> 原文:[https://www . geeksforgeeks . org/python-chunked-交错列表/](https://www.geeksforgeeks.org/python-chunked-interleave-of-lists/)

有时，在使用列表时，我们在执行合并操作时会遇到问题。更简单的版本易于实现。但是，当实现它的一个变体时，即我们需要交替地以块为单位交错的情况下，这就变成了一个更艰巨的任务。让我们讨论一下执行这项任务的具体方法。

**方法:使用 loop + `extend()`**
这个任务可以使用上面的功能来执行。在这种情况下，我们计算所需的迭代次数，然后运行一个循环。我们使用 extend()和指定的变量号在列表中添加元素。

```
# Python3 code to demonstrate 
# Chunked interleave of Lists
# using loop + extend()

# Initializing lists
test_list1 = [4, 5, 6, 8, 10, 11]
test_list2 = [6, 7, 8, 9, 8, 12]

# printing original lists 
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Initializing step
step = 3

# Chunked interleave of Lists
# using loop + extend()
num = len(test_list1)
iters = int(num / step) + 1
res = []
for idx in range(iters):
    start = step * idx
    end = step * (idx + 1)
    res.extend(test_list1[start : end])
    res.extend(test_list2[start : end])

# printing result 
print ("List after chunked merge : " + str(res))
```

**Output :**

```
The original list 1 is : [4, 5, 6, 8, 10, 11]
The original list 2 is : [6, 7, 8, 9, 8, 12]
List after chunked merge : [4, 5, 6, 6, 7, 8, 8, 10, 11, 9, 8, 12]

```