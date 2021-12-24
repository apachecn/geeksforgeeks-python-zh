# Python |从列表列表中删除列

> 原文:[https://www . geesforgeks . org/python-column-从列表中删除/](https://www.geeksforgeeks.org/python-column-deletion-from-list-of-lists/)

从列表中删除一行的问题很简单，我们只需要从列表中弹出一个列表。但是可以有一个实用程序，我们需要删除一列，即每个列表的特定索引元素。如果我们将任何数据库数据存储到容器中，就会出现这个问题。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`del + loop`**
在这个策略中，我们只需要在每次迭代时使用循环迭代行号来逐个删除列元素。

```py
# Python3 code to demonstrate 
# deleting columns of list of lists
# using del + loop

# initializing list 
test_list = [[4, 5, 6, 8],
             [2, 7, 10, 9],
             [12, 16, 18, 20]]

# printing original list
print ("The original list is : " + str(test_list))

# using del + loop
# deleting column element of row
for j in test_list:
    del j[1]

# printing result 
print ("The modified mesh after column deletion : " +  str(test_list))
```

**输出:**

> 原列表为:[[4，5，6，8]，[2，7，10，9]，[12，16，18，20]]
> 删除列后的修改网格:[[4，6，8]，[2，10，9]，[12，18，20]]

**方法 2:使用`pop() + list comprehension`**
我们可以使用列表理解技术和可用于移除列表元素的 pop 函数，以更简单和更短的方式完成这个特定任务。

```py
# Python3 code to demonstrate 
# deleting columns of list of lists
# using pop() + list comprehension

# initializing list 
test_list = [[4, 5, 6, 8],
             [2, 7, 10, 9],
             [12, 16, 18, 20]]

# printing original list
print ("The original list is : " + str(test_list))

# using pop() + list comprehension
# deleting column element of row
[j.pop(1) for j in test_list]

# printing result 
print ("The modified mesh after column deletion : " +  str(test_list))
```

**输出:**

> 原列表为:[[4，5，6，8]，[2，7，10，9]，[12，16，18，20]]
> 删除列后的修改网格:[[4，6，8]，[2，10，9]，[12，18，20]]