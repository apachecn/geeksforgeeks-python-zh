# Python |给整数列表中的每个元素添加 K

> 原文:[https://www . geesforgeks . org/python-向整数列表中的每个元素添加-k/](https://www.geeksforgeeks.org/python-adding-k-to-each-element-in-a-list-of-integers/)

在使用 Python 列表时，我们可以想到一种情况，即我们需要向列表中的每个元素添加整数 *k* 。我们可能需要迭代并将 *k* 添加到每个元素中，但是这会增加代码行。让我们讨论一下执行这项任务的某些人手不足的情况。

**方法#1:使用列表理解**
列表理解只是执行我们使用天真方法执行的任务的简单方法。这主要有助于节省时间，在代码可读性方面也是最好的。

```
# Python3 code to demonstrate 
# adding K to each element
# using list comprehension

# initializing list  
test_list = [4, 5, 6, 3, 9]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K
K = 4

# using list comprehension
# adding K to each element
res = [x + K for x in test_list]

# printing result 
print ("The list after adding K to each element : " +  str(res))
```

**输出:**

```
The original list is : [4, 5, 6, 3, 9]
The list after adding K to each element : [8, 9, 10, 7, 13]

```

**方法 2:使用`map()` + lambda**
映射函数可以将每个元素与 lambda 函数配对，lambda 函数执行将 *K* 添加到列表中每个元素的任务。

```
# Python3 code to demonstrate 
# adding K to each element
# using map() + lambda

# initializing list  
test_list = [4, 5, 6, 3, 9]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K
K = 4

# using map() + lambda
# adding K to each element
res = list(map(lambda x : x + K, test_list))

# printing result 
print ("The list after adding K to each element : " +  str(res))
```

**输出:**

```
The original list is : [4, 5, 6, 3, 9]
The list after adding K to each element : [8, 9, 10, 7, 13]

```

**方法 3:使用`map() + operator.add`**
这与上面的函数类似，但是使用 `operator.add`将每个元素添加到在应用地图函数之前形成的 *K* 的其他列表中的其他元素。它添加了列表中相似的索引元素。

```
# Python3 code to demonstrate 
# adding K to each element
# using map() + operator.add
import operator

# initializing list  
test_list = [4, 5, 6, 3, 9]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K list
K_list = [4] * len(test_list)

# using map() + operator.add
# adding K to each element
res = list(map(operator.add, test_list, K_list))

# printing result 
print ("The list after adding K to each element : " +  str(res))
```

**输出:**

```
The original list is : [4, 5, 6, 3, 9]
The list after adding K to each element : [8, 9, 10, 7, 13]

```