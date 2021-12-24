# Python |两个嵌套列表的交集

> 原文:[https://www . geesforgeks . org/python-两个嵌套列表的交集/](https://www.geeksforgeeks.org/python-intersection-of-two-nested-list/)

这篇特别的文章旨在实现交叉两个列表的任务，其中每个元素本身就是一个列表。这也是一个有用的工具，因为这种任务可以出现在程序员的生活中，如果他在开发世界中的话。让我们讨论一些完成这项任务的方法。

**方法 1:天真的方法**
这是完成这个任务最简单的方法，使用蛮力的方法执行一个循环，并检查一个列表是否包含与另一个列表相似的列表。

```py
# Python 3 code to demonstrate 
# find intersection of nested list
# using naive method

# initializing lists
test_list1 = [ [1, 2], [3, 4], [5, 6] ]
test_list2 = [ [3, 4], [5, 7], [1, 2] ]

# printing both lists 
print ("The original list 1 : " + str(test_list1))
print ("The original list 2 : " + str(test_list2))

# using naive method 
# to get list intersection
res_list = []
for i in test_list1:
    if i in test_list2:
        res_list.append(i)

# printing the intersection 
print ("The intersection of two lists is : " + str(res_list))
```

**输出:**

```py
The original list 1 : [[1, 2], [3, 4], [5, 6]]
The original list 2 : [[3, 4], [5, 7], [1, 2]]
The intersection of two lists is : [[1, 2], [3, 4]]

```

**方法 2:使用列表理解**
我们可以用相对较少的行数来执行如上所述的类似任务。但方法与上面类似，只是使用列表理解的方法来执行任务。

```py
# Python 3 code to demonstrate 
# find intersection of nested list
# using list comprehension

# initializing lists
test_list1 = [ [1, 2], [3, 4], [5, 6] ]
test_list2 = [ [3, 4], [5, 7], [1, 2] ]

# printing both lists 
print ("The original list 1 : " + str(test_list1))
print ("The original list 2 : " + str(test_list2))

# using list comprehension
# to get list intersection
res_list = [i for i in test_list1 if i in test_list2]

# printing the intersection 
print ("The intersection of two lists is : " + str(res_list))
```

输出:

```py
The original list 1 : [[1, 2], [3, 4], [5, 6]]
The original list 2 : [[3, 4], [5, 7], [1, 2]]
The intersection of two lists is : [[1, 2], [3, 4]]

```

**方法三:使用`set() + map()`和`&`**
执行这个任务最有效率和推荐的方法就是使用`set()`和`map()`的组合来实现。首先使用 map 将内部列表转换为元组，使用&运算符将外部列表转换为集合，可以执行集合交集，从而执行此任务。此外，如果需要以列表方式进入列表，我们可以使用`map()`将外容器和内容器转换回列表。

```py
# Python 3 code to demonstrate 
# find intersection of nested list
# using map() + set() + &

# initializing lists
test_list1 = [ [1, 2], [3, 4], [5, 6] ]
test_list2 = [ [3, 4], [5, 7], [1, 2] ]

# printing both lists 
print ("The original list 1 : " + str(test_list1))
print ("The original list 2 : " + str(test_list2))

# using map() + set() + &
# to get list intersection
res_set = set(map(tuple, test_list1)) & set(map(tuple, test_list2))
res_list = list(map(list, res_set))

# printing the intersection 
print ("The intersection of two lists is : " + str(res_list))
```

**输出:**

```py
The original list 1 : [[1, 2], [3, 4], [5, 6]]
The original list 2 : [[3, 4], [5, 7], [1, 2]]
The intersection of two lists is : [[1, 2], [3, 4]]

```