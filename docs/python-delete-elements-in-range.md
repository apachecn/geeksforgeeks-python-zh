# Python |删除范围内的元素

> 原文:[https://www . geesforgeks . org/python-delete-elements-in-range/](https://www.geeksforgeeks.org/python-delete-elements-in-range/)

删除单个元素相对容易，但是当我们希望删除范围内的元素时，由于 python 中列表元素的自动重新排列和移动，这个任务一度变得很乏味。让我们讨论在范围内删除元素的某些方法。

**方法#1:使用 del + `sorted()`**
在该方法中，我们将想要删除的索引列表反向，并以反向的方式在原始列表中删除它们，这样列表的重新排列不会破坏解决方案的完整性。

```py
# Python3 code to demonstrate
# range deletion of elements 
# using del + sorted()

# initializing list 
test_list = [3, 5, 6, 7, 2, 10]

# initializing indices
indices_list = [1, 4, 2]

# printing the original list
print ("The original list is : " + str(test_list))

# printing the indices list
print ("The indices list is : " + str(indices_list))

# using del + sorted()
# range deletion of elements
for i in sorted(indices_list, reverse = True):
    del test_list[i]

# printing result
print ("The modified deleted list is : " + str(test_list))
```

**Output:**

```py
The original list is : [3, 5, 6, 7, 2, 10]
The indices list is : [1, 4, 2]
The modified deleted list is : [3, 7, 10]

```

**方法 2:使用`enumerate()` +列表理解**
如果我们制作一个删除列表中不会有元素的列表，也可以执行这个任务，即不是实际删除元素，而是不用元素就可以重新制作。

```py
# Python3 code to demonstrate
# range deletion of elements 
# using enumerate() + list comprehension

# initializing list 
test_list = [3, 5, 6, 7, 2, 10]

# initializing indices
indices_list = [1, 4, 2]

# printing the original list
print ("The original list is : " + str(test_list))

# printing the indices list
print ("The indices list is : " + str(indices_list))

# using enumerate() + list comprehension
# range deletion of elements
test_list[:] = [ j for i, j in enumerate(test_list)
                         if i not in indices_list ]

# printing result
print ("The modified deleted list is : " + str(test_list))
```

**Output:**

```py
The original list is : [3, 5, 6, 7, 2, 10]
The indices list is : [1, 4, 2]
The modified deleted list is : [3, 7, 10]

```