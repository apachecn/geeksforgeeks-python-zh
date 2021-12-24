# 检查 Python 列表中是否存在元素

> 原文:[https://www . geesforgeks . org/check-if-element-exists-in-list-in-python/](https://www.geeksforgeeks.org/check-if-element-exists-in-list-in-python/)

列表在 python 中是一个重要的容器，就好像将所有数据类型的元素存储为一个集合。某些列表操作的知识对于日常编程是必要的。本文讨论了检查列表中元素是否存在的基本列表操作之一。

### **方法 1:天真法**

在 Naive 方法中，人们很容易使用一个循环来遍历所有元素，以检查目标元素的存在。这是检查列表中元素是否存在的最简单方法。

### **方法 2:在**中使用

Python 是检查一个元素是否存在于列表中的最常规的方法。如果列表中存在某个元素，这种特殊方式返回 True 如果列表中不存在该元素，则返回 False。练习这种检查方法不需要对列表进行排序。

**代码#1:** 演示使用天真方法和中的*检查列表中元素的存在。*

## 蟒蛇 3

```py
# Python code to demonstrate
# checking of element existence
# using loops and in

# Initializing list
test_list = [ 1, 6, 3, 5, 3, 4 ]

print("Checking if 4 exists in list ( using loop ) : ")

# Checking if 4 exists in list
# using loop
for i in test_list:
    if(i == 4) :
        print ("Element Exists")

print("Checking if 4 exists in list ( using in ) : ")

# Checking if 4 exists in list
# using in
if (4 in test_list):
    print ("Element Exists")
```

**输出:**

```py
Checking if 4 exists in list ( using loop ) : 
Element Exists
Checking if 4 exists in list ( using in ) : 
Element Exists
```

### **方法三:使用** [**设定()**](https://www.geeksforgeeks.org/python-set-method/) **+在**

将列表转换为集合，然后在中使用*可能比只在中使用更有效。但是有效率也有一定的负面影响。其中之一是列表的顺序没有被保留，如果你选择为它取一个新的列表，你将需要使用额外的空间。另一个缺点是 set 不允许重复，因此重复的元素将从原始列表中删除。* 

### **方法四:使用** [**排序()**](https://www.geeksforgeeks.org/python-list-sort/) **+** [**平分 _ 左()**](https://www.geeksforgeeks.org/binary-search-bisect-in-python/)

测试元素存在的常规二分搜索法方法，因此列表必须首先排序，因此不保留元素顺序。[平分 _left()](https://www.geeksforgeeks.org/binary-search-bisect-in-python/) 返回要查找的元素的第一次出现，其工作方式类似于 C++ STL 中的[下界()](https://www.geeksforgeeks.org/lower_bound-in-cpp/)。

> **注意:**等分函数只会说明插入元素的位置，而不会说明元素是否存在的细节。

**代码#2 :** 演示如何使用 set() + in 和 sort() +平分 _left()检查列表中元素的存在。

## 蟒蛇 3

```py
# Python code to demonstrate
# checking of element existence
# using set() + in
# using sort() + bisect_left()
from bisect import bisect_left ,bisect

# Initializing list
test_list_set = [ 1, 6, 3, 5, 3, 4 ]
test_list_bisect = [ 1, 6, 3, 5, 3, 4 ]

print("Checking if 4 exists in list ( using set() + in) : ")

# Checking if 4 exists in list
# using set() + in
test_list_set = set(test_list_set)
if 4 in test_list_set :
    print ("Element Exists")

print("Checking if 4 exists in list ( using sort() + bisect_left() ) : ")

# Checking if 4 exists in list
# using sort() + bisect_left()
test_list_bisect.sort()
if bisect_left(test_list_bisect, 4)!=bisect(test_list_bisect, 4):
    print ("Element Exists")
else:
    print("Element doesnt exist")
```

### **方法五:使用** [**计数()**](https://www.geeksforgeeks.org/python-list-function-count/)

我们可以使用内置的 python List 方法 count()，来检查传递的元素是否存在于 List 中。如果传递的元素存在于列表中， [count()](https://www.geeksforgeeks.org/python-list-function-count/) 方法将显示它在整个列表中出现的次数。如果是非零正数，则表示列表中存在元素。

**代码#3** :演示使用[计数()](https://www.geeksforgeeks.org/python-list-function-count/)检查列表中元素的存在。

## 蟒蛇 3

```py
"""
Python code to demonstrate
checking of element existence
using List count() method
"""

# Initializing list
test_list = [10, 15, 20, 7, 46, 2808]

print("Checking if 15 exists in list")

# number of times element exists in list
exist_count = test_list.count(15)

# checking if it is more then 0
if exist_count > 0:
    print("Yes, 15 exists in list")
else:
    print("No, 15 does not exists in list")
```