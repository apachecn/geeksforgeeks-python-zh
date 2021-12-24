# Python |借助索引在列表中添加元素

> 原文:[https://www . geesforgeks . org/python-借助索引在列表中添加元素/](https://www.geeksforgeeks.org/python-add-the-element-in-the-list-with-help-of-indexing/)

使用 append 函数可以很容易地向列表中添加元素。但是在竞争性编程中，我们有时可能需要记忆，因此我们需要在索引的帮助下在列表中添加元素，也就是说，在填充之前的索引之前填充后面的索引。在正常情况下执行此操作会输出错误，因为事先没有为列表分配内存。让我们讨论一下实现这一点的某些方法。

**方法#1:用 `None`**
使用预初始化这个问题的解决方案可以通过这样一个事实来实现，如果我们用无初始化所有的元素，内存将被分配给列表，然后它可以在以后根据需要被覆盖。

```
# Python3 code to demonstrate 
# indexing element in list
# pre initializing with None

# initializing list
test_list =  [None] * 50

# assigning value 
test_list[5] = 24 

# printing inserted element 
print ("The inserted element is : " + str(test_list[5]))
```

**输出:**

```
The inserted element is : 24

```

**方法 2:使用字典**
这种技术不一定要创建列表，而是创建了字典，该字典又可以代替列表使用，并可以执行类似的索引任务。这个方法正好解决了上面提到的问题。

```
# Python3 code to demonstrate 
# indexing element in list
# using dictionary

# initializing list
test_list =  {}

# assigning value 
test_list[5] = 24 

# printing inserted element 
print ("The inserted element is : " + str(test_list[5]))
```

**输出:**

```
The inserted element is : 24

```