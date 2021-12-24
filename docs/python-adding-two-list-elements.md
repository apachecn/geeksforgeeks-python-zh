# Python |添加两个列表元素

> 原文:[https://www . geesforgeks . org/python-添加-双列表-元素/](https://www.geeksforgeeks.org/python-adding-two-list-elements/)

在许多情况下，人们需要对两个不同的列表进行索引求和。这在日常编程中可能会有应用。让我们讨论执行这项任务的各种方法。

**方法#1:天真的方法**
在这个方法中，我们简单地运行一个循环，并将两个列表元素在相似索引处的总和附加到新列表中，直到我们到达较小列表的末尾。这是完成这项任务的基本方法。

```py
# Python code to demonstrate 
# addition of two list 
# naive method 

# initializing lists
test_list1 = [1, 3, 4, 6, 8]
test_list2 = [4, 5, 6, 2, 10]

# printing original lists
print ("Original list 1 : " + str(test_list1))
print ("Original list 2 : " + str(test_list2))

# using naive method to 
# add two list 
res_list = []
for i in range(0, len(test_list1)):
    res_list.append(test_list1[i] + test_list2[i])

# printing resultant list 
print ("Resultant list is : " + str(res_list))
```

**输出:**

```py
Original list 1 : [1, 3, 4, 6, 8]
Original list 2 : [4, 5, 6, 2, 10]
Resultant list is : [5, 8, 10, 8, 18]

```

**方法 2:使用列表理解**
作为上面解释的技术的简写，列表理解通常打字更快，因此必须优先执行这类编程任务。

```py
# Python code to demonstrate 
# addition of two list 
# list comprehension

# initializing lists
test_list1 = [1, 3, 4, 6, 8]
test_list2 = [4, 5, 6, 2, 10]

# printing original lists
print ("Original list 1 : " + str(test_list1))
print ("Original list 2 : " + str(test_list2))

# using list comprehension to 
# add two list 
res_list = [test_list1[i] + test_list2[i] for i in range(len(test_list1))]

# printing resultant list 
print ("Resultant list is : " + str(res_list))
```

**输出:**

```py
Original list 1 : [1, 3, 4, 6, 8]
Original list 2 : [4, 5, 6, 2, 10]
Resultant list is : [5, 8, 10, 8, 18]

```

**方法 3:使用`map() + add()`**
`map()`也可以使用，因为我们可以将添加操作连同两个列表一起输入到`map()`中，`map()`可以执行这两种技术的添加。这可以扩展到任何可能的数学运算。

```py
# Python code to demonstrate 
# addition of two list 
# map() + add()
from operator import add

# initializing lists
test_list1 = [1, 3, 4, 6, 8]
test_list2 = [4, 5, 6, 2, 10]

# printing original lists
print ("Original list 1 : " + str(test_list1))
print ("Original list 2 : " + str(test_list2))

# using map() + add() to 
# add two list 
res_list = list(map(add, test_list1, test_list2))

# printing resultant list 
print ("Resultant list is : " + str(res_list))
```

**输出:**

```py
Original list 1 : [1, 3, 4, 6, 8]
Original list 2 : [4, 5, 6, 2, 10]
Resultant list is : [5, 8, 10, 8, 18]

```

**方法 4:使用`zip() + sum()`**
`sum()`可以对可以使用`zip()`一起“压缩”的列表进行索引式添加。这是执行这项特殊任务的非常优雅的方式。

```py
# Python code to demonstrate 
# addition of two list 
# zip() + sum()
from operator import add

# initializing lists
test_list1 = [1, 3, 4, 6, 8]
test_list2 = [4, 5, 6, 2, 10]

# printing original lists
print ("Original list 1 : " + str(test_list1))
print ("Original list 2 : " + str(test_list2))

# using zip() + sum() to 
# add two list 
res_list = [sum(i) for i in zip(test_list1, test_list2)]

# printing resultant list 
print ("Resultant list is : " + str(res_list))
```

**输出:**

```py
Original list 1 : [1, 3, 4, 6, 8]
Original list 2 : [4, 5, 6, 2, 10]
Resultant list is : [5, 8, 10, 8, 18]

```