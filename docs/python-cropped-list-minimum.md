# Python |裁剪列表最小值

> 原文:[https://www.geeksforgeeks.org/python-cropped-list-minimum/](https://www.geeksforgeeks.org/python-cropped-list-minimum/)

有时，我们要求通过删除列表的某些元素来缩小列表。用来执行这个特殊任务的方法之一是前后元素删除，我们也希望找到这个列表的最小值。这是一个很好的工具，它的解决方案可能是有用的。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表切片+ del 操作符+min()**
del 操作符可以通过切片操作来删除列表中的前后元素，从而获得列表的裁剪版本。使用 min()可以找到寻找最小值的任务。

```py
# Python3 code to demonstrate 
# Cropped list Minimum
# using del operator + list slicing + min()

# initializing list 
test_list = [2, 3, 5, 7, 9, 10, 8, 6]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K 
K = 2

# using del operator + list slicing + min()
# Cropped list Minimum
del test_list[-K:], test_list[:K]
res = min(test_list)

# printing result 
print ("The cropped list minimum is : " + str(res))
```

**Output :**

```py
The original list is : [2, 3, 5, 7, 9, 10, 8, 6]
The cropped list minimum is : 5

```