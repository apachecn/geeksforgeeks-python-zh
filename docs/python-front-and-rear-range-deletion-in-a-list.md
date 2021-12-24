# Python |列表中前后范围删除

> 原文:[https://www . geesforgeks . org/python-前后范围-列表中删除/](https://www.geeksforgeeks.org/python-front-and-rear-range-deletion-in-a-list/)

有时，我们要求通过删除列表的某些元素来缩小列表。用于执行该特定任务的方法之一是前后元素删除。这是一个很好的工具，它的解决方案可能是有用的。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表切片+ `del`操作符**
`del`操作符可以通过切片动作来删除列表中的前后元素，从而获得列表的裁剪版本。

```py
# Python3 code to demonstrate 
# front and rear deletion 
# using del operator + list slicing

# initializing list 
test_list = [2, 3, 5, 7, 9, 10, 8, 6]

# printing original list
print ("The original list is : " + str(test_list))

# using del operator + list slicing
# front and rear deletion 
del test_list[-2:], test_list[:2]

# printing result 
print ("The cropped list is : " +  str(test_list))
```

输出:

```py
The original list is : [2, 3, 5, 7, 9, 10, 8, 6]
The cropped list is : [5, 7, 9, 10]

```

**方法#2:使用列表切片**
可以修改上述方法，并且可以省略 del 运算符的使用来实现该特定任务。我们可以通过从列表中移除特定数量的元素的方式来分割列表。

```py
# Python3 code to demonstrate 
# front and rear deletion 
# using list slicing

# initializing list 
test_list = [2, 3, 5, 7, 9, 10, 8, 6]

# printing original list
print ("The original list is : " + str(test_list))

# using list slicing
# front and rear deletion 
res = test_list[2 : -2]

# printing result 
print ("The cropped list is : " +  str(res))
```

输出:

```py
The original list is : [2, 3, 5, 7, 9, 10, 8, 6]
The cropped list is : [5, 7, 9, 10]

```