# Python |访问列表中的索引和值

> 原文:[https://www . geesforgeks . org/python-访问列表中的索引和值/](https://www.geeksforgeeks.org/python-accessing-index-and-value-in-list/)

有各种方法可以访问列表的元素，但是有时我们可能需要访问元素以及找到它的索引。

让我们看看访问列表中索引和值的所有不同方式。

**方法#1 :** 幼稚方法

这是最通用的方法，可以用来执行访问索引和列表元素值的任务。这是使用循环完成的。

```py
# Python3 code to demonstrate 
# to get index and value
# using naive method

# initializing list
test_list = [1, 4, 5, 6, 7]

# Printing list 
print ("Original list is : " + str(test_list))

# using naive method to
# get index and value
print ("List index-value are : ")
for i in range(len(test_list)):
    print (i, end = " ")
    print (test_list[i])
```

**Output:**

```py
Original list is : [1, 4, 5, 6, 7]
List index-value are : 
0 1
1 4
2 5
3 6
4 7

```

**方法二:**使用[列表理解](https://www.geeksforgeeks.org/pya thon-list-comprehension-and-slicing/)

这个方法的工作方式与上面的方法类似，但是使用了列表理解技术，这减少了可能要编写的代码行，因此节省了时间。

```py
# Python3 code to demonstrate 
# to get index and value
# using list comprehension

# initializing list
test_list = [1, 4, 5, 6, 7]

# Printing list 
print ("Original list is : " + str(test_list))

# using list comprehension to
# get index and value
print ("List index-value are : ")
print ([list((i, test_list[i])) for i in range(len(test_list))])
```

**Output:**

```py
Original list is : [1, 4, 5, 6, 7]
List index-value are : 
[[0, 1], [1, 4], [2, 5], [3, 6], [4, 7]]

```

**方法 3 :** 使用`enumerate()`

这是解决这个特殊问题的最优雅的方法，强烈建议在我们需要获取索引和列表中的值的情况下使用。此方法枚举索引及其值。

```py
# Python3 code to demonstrate 
# to get index and value
# using enumerate

# initializing list
test_list = [1, 4, 5, 6, 7]

# Printing list 
print ("Original list is : " + str(test_list))

# using enumerate to
# get index and value
print ("List index-value are : ")
for index, value in enumerate(test_list):
    print(index, value)
```

**Output:**

```py
Original list is : [1, 4, 5, 6, 7]
List index-value are : 
0 1
1 4
2 5
3 6
4 7

```

**方法#4 :** 使用`zip()`
另一种基本上用于将索引与相应值绑定的方法，`zip()`也可能用于获取索引及其值。

```py
# Python3 code to demonstrate 
# to get index and value
# using zip()

# initializing list
test_list = [1, 4, 5, 6, 7]

# Printing list 
print ("Original list is : " + str(test_list))

# using zip() to
# get index and value
print ("List index-value are : ")
for index, value in zip(range(len(test_list)), test_list):
    print (index, value)
```

**Output:**

```py
Original list is : [1, 4, 5, 6, 7]
List index-value are : 
0 1
1 4
2 5
3 6
4 7

```