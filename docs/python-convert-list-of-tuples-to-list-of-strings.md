# Python |将元组列表转换为字符串列表

> 原文:[https://www . geesforgeks . org/python-convert-list-of-tuples-to-list-strings/](https://www.geeksforgeeks.org/python-convert-list-of-tuples-to-list-of-strings/)

数据类型之间的相互转换是非常有用的工具，许多文章都是这样写的。本文讨论了字符元组到单个字符串之间的相互转换。这种相互转换在机器学习中很有用，在机器学习中，我们需要以特定的格式给出训练模型的输入。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `join()`**
列表理解执行迭代整个元组列表的任务，连接函数执行将元组的元素聚合成一个列表的任务。

```
# Python3 code to demonstrate
# conversion of list of tuple to list of list 
# using list comprehension + join()

# initializing list 
test_list = [('G', 'E', 'E', 'K', 'S'), ('F', 'O', 'R'),
                              ('G', 'E', 'E', 'K', 'S')]

# printing the original list
print ("The original list is : " + str(test_list))

# using list comprehension + join()
# conversion of list of tuple to list of list 
res = [''.join(i) for i in test_list]

# printing result
print ("The list after conversion to list of string : " + str(res))
```

**输出:**

> 原列表为:[('G '，' E '，' E '，' K '，' S ')，(' F '，' O '，' R ')，(' G '，' E '，' E '，' K '，' S')]
> 转换为列表后的列表为字符串:['GEEKS '，' FOR '，' GEEKS']

**方法 2:使用`map() + join()`**
列表理解执行的任务可以通过映射函数来执行，映射函数可以将一个元组的逻辑扩展到列表中的所有元组。

```
# Python3 code to demonstrate
# conversion of list of tuple to list of list 
# using map() + join()

# initializing list 
test_list = [('G', 'E', 'E', 'K', 'S'), ('F', 'O', 'R'),
                              ('G', 'E', 'E', 'K', 'S')]

# printing the original list
print ("The original list is : " + str(test_list))

# using map() + join()
# conversion of list of tuple to list of list 
res = list(map(''.join, test_list))

# printing result
print ("The list after conversion to list of string : " + str(res))
```

**输出:**

> 原列表为:[('G '，' E '，' E '，' K '，' S ')，(' F '，' O '，' R ')，(' G '，' E '，' E '，' K '，' S')]
> 转换为列表后的列表为字符串:['GEEKS '，' FOR '，' GEEKS']