# Python |二进制列表到整数

> 原文:[https://www . geesforgeks . org/python-二进制列表到整数/](https://www.geeksforgeeks.org/python-binary-list-to-integer/)

本文中讨论的问题很常见，每个程序员都会遇到。二进制数字列表到其整数值的转换可以使用速记来完成，并且对它们的了解可以证明是非常有用的。让我们讨论一下实现这一点的某些方法。

**方法一:使用`join()` +列表理解**
这两个功能的结合可以帮助完成这个特定的任务。在此方法中，首先将整个列表转换为字符串，然后将类型转换为 int，然后获得二进制数。

```
# Python3 code to demonstrate 
# converting binary list to integer 
# using join() + list comprehension

# initializing list 
test_list = [1, 0, 0, 1, 1, 0]

# printing original list
print ("The original list is : " + str(test_list))

# using join() + list comprehension
# converting binary list to integer 
res = int("".join(str(x) for x in test_list), 2)

# printing result 
print ("The converted integer value is : " +  str(res))
```

**输出:**

```
The original list is : [1, 0, 0, 1, 1, 0]
The converted integer value is : 38

```

**方法#2:使用位移位+ `| operator`**
这个特殊的任务可以通过移位位并对每个被处理的位取|来执行。这是另一种优雅的执行方式。

```
# Python3 code to demonstrate 
# converting binary list to integer 
# using bit shift + | operator

# initializing list 
test_list = [1, 0, 0, 1, 1, 0]

# printing original list
print ("The original list is : " + str(test_list))

# using bit shift + | operator
# converting binary list to integer 
res = 0
for ele in test_list:
    res = (res << 1) | ele

# printing result 
print ("The converted integer value is : " +  str(res))
```

**输出:**

```
The original list is : [1, 0, 0, 1, 1, 0]
The converted integer value is : 38

```