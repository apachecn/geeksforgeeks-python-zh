# Python |将多列表中相同索引的元素分组

> 原文:[https://www . geesforgeks . org/python-group-elements-at-at-indexes-in-a-a-multi-list/](https://www.geeksforgeeks.org/python-group-elements-at-same-indices-in-a-multi-list/)

将 2D 列表展平为一个是许多领域面临的常见问题。但有时我们需要将特定索引处的元素配对为一个，这样各个索引处的元素就在一起了。这个问题并不常见，但有一个解决方案还是有帮助的。

让我们讨论在特定索引处配对元素的某些方法。

**方法#1:使用列表理解+ `zip()`**
列表理解可以用来实现这个特殊的任务，以及将相似的索引配对在一起的 zip 功能。这个方法只是简单方法的简写。

```py
# Python3 code to demonstrate 
# index list elements pairing
# using list comprehension 

# initializing list  
test_list = [[1, 4, 5], [4, 6, 8], [8, 3, 10]]

# printing original list
print ("The original list is : " + str(test_list))

# using list comprehension  
# to perform index list elements pairing
res = [list(x) for x in zip(*test_list)]

# printing result
print ("The index elements pairs list is " + str(res))
```

**Output:**

```py
The original list is : [[1, 4, 5], [4, 6, 8], [8, 3, 10]]
The index elements pairs list is [[1, 4, 8], [4, 6, 3], [5, 8, 10]]

```

**方法 2:使用`map() + zip()`**
`map` 函数可以将每个迭代结果映射到单个列表中，而`zip` 函数执行索引元素配对。这种结合可以用来达到预期的效果。

```py
# Python3 code to demonstrate 
# index list elements pairing
# using map() + zip()

# initializing list  
test_list = [[1, 4, 5], [4, 6, 8], [8, 3, 10]]

# printing original list
print ("The original list is : " + str(test_list))

# using map() + zip()  
# to perform index list elements pairing
res = list(map(list, zip(*test_list)))

# printing result
print ("The index elements pairs list is " + str(res))
```

**Output:**

```py
The original list is : [[1, 4, 5], [4, 6, 8], [8, 3, 10]]
The index elements pairs list is [[1, 4, 8], [4, 6, 3], [5, 8, 10]]

```

**方法三:使用`zip()`**
单独使用`zip` 功能就可以了，只需要将其类型转换为列表，以列表格式打印结果即可。这是完成这项任务的最敏捷的方式，也是最优雅的方式。

```py
# Python3 code to demonstrate 
# index list elements pairing
# using zip()

# initializing list  
test_list = [[1, 4, 5], [4, 6, 8], [8, 3, 10]]

# printing original list
print ("The original list is : " + str(test_list))

# using zip()  
# to perform index list elements pairing
res = list(zip(*test_list))

# printing result
print ("The index elements pairs list is " + str(res))
```

**Output:**

```py
The original list is : [[1, 4, 5], [4, 6, 8], [8, 3, 10]]
The index elements pairs list is [(1, 4, 8), (4, 6, 3), (5, 8, 10)]

```