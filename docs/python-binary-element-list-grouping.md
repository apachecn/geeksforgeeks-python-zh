# Python |二进制元素列表分组

> 原文:[https://www . geesforgeks . org/python-binary-element-list-group/](https://www.geeksforgeeks.org/python-binary-element-list-grouping/)

有时在使用数据库时，我们需要执行某些更像查询语言的列表操作，例如，将嵌套的列表元素相对于它的其他索引元素进行分组。本文讨论二进制嵌套列表，并将每个嵌套列表元素与其他索引元素进行分组

**方法一:使用列表理解**
列表理解可以完成通常需要 1-2 行 4-5 行的任务。这通过根据与列表中另一个元素的匹配为每个数值赋值来对元素进行分组。

```py
# Python3 code to demonstrate 
# to perform binary list grouping
# using list comprehension

# initializing list 
test_list = [["G", 0], ["F", 0], ["B", 2],
             ["E", 2], ['I', 1], ['S', 1],
             ['S', 2], ['T', 2], ['G', 0]]

# using list comprehension
# to perform binary list grouping
temp = set(map(lambda i : i[1], test_list))
res =  [[j[0] for j in test_list if j[1] == i] for i in temp]

# printing result
print ("The grouped list is : " +  str(res))
```

**Output:**

```py
The grouped list is : [['G', 'F', 'G'], ['I', 'S'], ['B', 'E', 'S', 'T']]

```