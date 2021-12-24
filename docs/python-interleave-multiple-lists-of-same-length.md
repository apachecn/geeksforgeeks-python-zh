# Python |交错多个相同长度的列表

> 原文:[https://www . geeksforgeeks . org/python-interlace-multi-list-同长/](https://www.geeksforgeeks.org/python-interleave-multiple-lists-of-same-length/)

给定相同长度的列表，编写一个 Python 程序，将给定列表的可选元素存储在一个新列表中。

让我们讨论一下实现这一点的某些方法。

**方法#1:使用`map() + list comprehension`**
`map()`处理列表的交错，交替插入的任务由简写代码的列表理解部分完成。只在 Python 2 中有效。

```
# Python2 code to demonstrate 
# to interleave lists
# using map() + list comprehension

# initializing lists 
test_list1 = [1, 4, 5]
test_list2 = [3, 8, 9]

# printing original lists
print ("Original list 1 : " + str(test_list1))
print ("Original list 2 : " + str(test_list2))

# using map() + list comprehension
# to interleave lists
res = [i for j in map(None, test_list1, test_list2)  
                       for i in j if i is not None]

# printing result
print ("The interleaved list is : " + str(res))
```

**Output:**

```
Original list 1 : [1, 4, 5]
Original list 2 : [3, 8, 9]
The interleaved list is : [1, 3, 4, 8, 5, 9]

```

**方法 2:使用列表切片**
python 的列表切片的力量也可以用来执行这个特定的任务。我们首先将一个列表扩展到另一个列表，然后允许原始列表成为结果列表的期望替代索引。

```
# Python3 code to demonstrate 
# to interleave lists
# using list slicing

# initializing lists 
test_list1 = [1, 4, 5]
test_list2 = [3, 8, 9]

# printing original lists
print ("Original list 1 : " + str(test_list1))
print ("Original list 2 : " + str(test_list2))

# using list slicing
# to interleave lists
res = test_list1 + test_list2
res[::2] = test_list1
res[1::2] = test_list2

# printing result
print ("The interleaved list is : " + str(res))
```

**Output:**

```
Original list 1 : [1, 4, 5]
Original list 2 : [3, 8, 9]
The interleaved list is : [1, 3, 4, 8, 5, 9]

```

**方法 3:使用`itertools.chain() + zip()`**
`zip()`可以链接两个列表，然后`chain()`可以根据需要执行元素的交替追加。这是执行这项任务最有效的方法。

```
# Python3 code to demonstrate 
# to interleave lists
# using zip() + itertools.chain()
import itertools

# initializing lists 
test_list1 = [1, 4, 5]
test_list2 = [3, 8, 9]

# printing original lists
print ("Original list 1 : " + str(test_list1))
print ("Original list 2 : " + str(test_list2))

# using zip() + itertools.chain()
# to interleave lists
res = list(itertools.chain(*zip(test_list1, test_list2)))

# printing result
print ("The interleaved list is : " + str(res))
```

**Output:**

```
Original list 1 : [1, 4, 5]
Original list 2 : [3, 8, 9]
The interleaved list is : [1, 3, 4, 8, 5, 9]

```