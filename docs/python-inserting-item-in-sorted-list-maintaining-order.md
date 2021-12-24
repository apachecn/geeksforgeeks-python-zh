# Python |在排序列表中插入项目维护顺序

> 原文:[https://www . geesforgeks . org/python-插入-排序列表中的项目-维护-顺序/](https://www.geeksforgeeks.org/python-inserting-item-in-sorted-list-maintaining-order/)

使用排序列表是必不可少的，因为我们得到的数据大多是有序的。任何查询都可以将新数据插入到适当的位置。因此需要知道如何执行这些动态查询。让我们讨论一下实现这一点的某些方法。

**方法#1:天真方法**
在这个方法中，我们只是简单地测试值，并检查下一个元素是否大于输入元素，并存储索引，然后用于在该位置对该元素进行切片。

```py
# Python3 code to demonstrate 
# insertion in sorted list
# using naive method 

# initializing list
test_list = [1, 2, 3, 6, 7]

# printing original list
print ("The original list is : " + str(test_list))

# insert element
k = 5

# using naive method 
# insertion in sorted list
# using naive method 
for i in range(len(test_list)):
    if test_list[i] > k:
        index = i
        break
res = test_list[: i] + [k] + test_list[i :]

# printing result
print ("The list after insertion is : " +  str(res))
```

**Output:**

```py
The original list is : [1, 2, 3, 6, 7]
The list after insertion is : [1, 2, 3, 5, 6, 7]

```

**方法#2:使用`bisect.insort()`**
这是执行这个特定任务更简洁和推荐的方法。这个方法是为这个特殊的任务设计的，并且以最有效的方式执行这个任务。

```py
# Python3 code to demonstrate 
# insertion in sorted list
# using bisect.insort()
import bisect

# initializing list
test_list = [1, 2, 3, 6, 7]

# printing original list
print ("The original list is : " + str(test_list))

# insert element
k = 5

# using bisect.insort()
# insertion in sorted list
# using naive method 
bisect.insort(test_list, k) 

# printing result
print ("The list after insertion is : " +  str(test_list))
```

**Output:**

```py
The original list is : [1, 2, 3, 6, 7]
The list after insertion is : [1, 2, 3, 5, 6, 7]

```