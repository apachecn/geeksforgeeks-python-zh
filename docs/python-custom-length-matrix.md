# Python |自定义长度矩阵

> 原文:[https://www.geeksforgeeks.org/python-custom-length-matrix/](https://www.geeksforgeeks.org/python-custom-length-matrix/)

有时，我们需要在 Python 中从包含元素的列表中初始化一个可变长度的矩阵。在本文中，我们将讨论可变长度方法的初始化以及一些实现方法。让我们讨论执行此操作的特定方法。

**方法一:使用`zip()` +列表理解**
zip 功能结合列表理解可以帮助完成这个特殊的任务。zip 函数可以帮助将计数器列表与元素列表进行压缩，列表理解完成矩阵的构造工作。

```
# Python3 code to demonstrate  
# Custom length Matrix 
# using zip() + list comprehension

# initializing list
test_list = ['a', 'b', 'c']

# initializing counter list 
counter_list = [1, 4, 2]

# printing original list 
print ("The original list is : " + str(test_list))

# printing counter list 
print ("The counter list is : " + str(counter_list))

# using zip() + list comprehension
# Custom length Matrix 
res = [[i] * j for i, j in zip(test_list, counter_list)]

# printing result
print ("The custom length matrix is : " + str(res))
```

**Output :**

```
The original list is : ['a', 'b', 'c']
The counter list is : [1, 4, 2]
The custom length matrix is : [['a'], ['b', 'b', 'b', 'b'], ['c', 'c']]

```