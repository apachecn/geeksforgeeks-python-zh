# Python |将字符串列表转换为列表列表

> 原文:[https://www . geesforgeks . org/python-convert-list-of-string-to-list/](https://www.geeksforgeeks.org/python-convert-list-of-string-to-list-of-list/)

很多时候，我们会遇到以字符串格式找到的转储数据，并要求将其表示为实际找到的实际列表格式。这种将字符串格式的列表转换回列表来执行任务的问题在 web 开发中非常常见。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`strip() + split()`**
结合剥离和拆分功能可以执行特定的任务。strip 函数可以用来去掉括号，split 函数可以使数据列表用逗号分隔。

```py
# Python3 code to demonstrate 
# to convert list of string to list of list
# using strip() + split()

# initializing list  
test_list = [ '[1, 4, 5]', '[4, 6, 8]' ]

# printing original list
print ("The original list is : " + str(test_list))

# using strip() + split()
# to convert list of string to list of list
res = [i.strip("[]").split(", ") for i in test_list]

# printing result 
print ("The list after conversion is : " +  str(res))
```

**输出:**

```py
The original list is : ['[1, 4, 5]', '[4, 6, 8]']
The list after conversion is : [['1', ' 4', ' 5'], ['4', ' 6', ' 8']]

```

**方法 2:使用列表切片和`split()`**
在上面的方法中执行的任务也可以使用列表切片来执行，其中我们从第二个到第二个最后一个元素切片所有元素，因此省略了最后一个括号。

```py
# Python3 code to demonstrate 
# to convert the list of string to list of list
# using list slicing + split()

# initializing list  
test_list = [ '[1, 4, 5]', '[4, 6, 8]' ]

# printing original list
print ("The original list is : " + str(test_list))

# using list slicing + split()
# to convert list of string to list of list
res = [i[1 : -1].split(', ') for i in test_list]

# printing result 
print ("The list after conversion is : " +  str(res))
```

**输出:**

```py
The original list is : ['[1, 4, 5]', '[4, 6, 8]']
The list after conversion is : [['1', ' 4', ' 5'], ['4', ' 6', ' 8']]

```