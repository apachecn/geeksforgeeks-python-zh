# Python |按元素连接两个列表

> 原文:[https://www . geesforgeks . org/python-concatenate-two-list-element-wise/](https://www.geeksforgeeks.org/python-concatenate-two-lists-element-wise/)

有时我们会遇到这种类型的问题，我们需要将一个列表中的每个元素与另一个一起留下。这类问题通常发生在我们拥有综合信息的开发中，比如不同列表中的姓名。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `zip()`**
列表理解完成连接相似索引元素的任务。zip 函数的任务是将结果字符串连接成单个列表和返回列表。

```py
# Python3 code to demonstrate 
# interlist element concatenation
# using list comprehension + zip()

# initializing lists  
test_list1 = ["Geeksfor", "i", "be"]
test_list2 = ['Geeks', 's', 'st']

# printing original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# using list comprehension + zip()
# interlist element concatenation
res = [i + j for i, j in zip(test_list1, test_list2)]

# printing result 
print ("The list after element concatenation is : " +  str(res))
```

**Output:**

```py
The original list 1 is : ['Geeksfor', 'i', 'be']
The original list 2 is : ['Geeks', 's', 'st']
The list after element concatenation is : ['GeeksforGeeks', 'is', 'best']

```

**方法 2:使用`map() + lambda + zip()`**
在该方法中，每个索引元素之间的映射任务由 map 函数执行，加法功能由 lambda 函数执行。这个方法只在 Python2 中有效。

```py
# Python code to demonstrate 
# interlist element concatenation
# using map() + lambda + zip()

# initializing lists  
test_list1 = ["Geeksfor", "i", "be"]
test_list2 = ['Geeks', 's', 'st']

# printing original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# using map() + lambda + zip()
# interlist element concatenation
res = list(map(lambda(i, j): i + j, zip(test_list1, test_list2)))

# printing result 
print ("The list after element concatenation is : " +  str(res))
```

**Output:**

```py
The original list 1 is : ['Geeksfor', 'i', 'be']
The original list 2 is : ['Geeks', 's', 'st']
The list after element concatenation is : ['GeeksforGeeks', 'is', 'best']

```