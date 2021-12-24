# Python |在列表中查找给定子串的字符串

> 原文:[https://www . geesforgeks . org/python-查找列表中带有给定子字符串的字符串/](https://www.geeksforgeeks.org/python-finding-strings-with-given-substring-in-list/)

Python 可以很容易处理的经典问题，也已经处理过很多次了，就是找出一个字符串是否是其他字符串的子串。但有时，人们希望在字符串列表中扩展这一点，因此需要遍历整个容器并执行通用算法。

让我们讨论在列表中查找给定子串的特定方法。

**方法#1:使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)**
列表理解是执行任何特定任务的优雅方式，因为从长远来看，它增加了可读性。这项任务可以用简单的方法完成，因此也可以简化为列表理解。

```
# Python code to demonstrate 
# to find strings with substrings 
# using list comprehension 

# initializing list 
test_list = ['GeeksforGeeks', 'Geeky', 'Computers', 'Algorithms']

# printing original list 
print ("The original list is : " + str(test_list))

# initializing substring
subs = 'Geek'

# using list comprehension 
# to get string with substring 
res = [i for i in test_list if subs in i]

# printing result 
print ("All strings with given substring are : " + str(res))
```

**Output:**

```
The original list is : ['GeeksforGeeks', 'Geeky', 'Computers', 'Algorithms']
All strings with given substring are : ['GeeksforGeeks', 'Geeky']

```

**方法二:使用 [`filter()` + lambda](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)**
这个功能也可以在 lambda 的帮助下执行这个寻找字符串的任务。它只是过滤掉所有匹配特定子字符串的字符串，然后将其添加到一个新列表中。

```
# Python code to demonstrate 
# to find strings with substrings 
# using filter() + lambda

# initializing list 
test_list = ['GeeksforGeeks', 'Geeky', 'Computers', 'Algorithms']

# printing original list 
print ("The original list is : " + str(test_list))

# initializing substring
subs = 'Geek'

# using filter() + lambda 
# to get string with substring 
res = list(filter(lambda x: subs in x, test_list))

# printing result 
print ("All strings with given substring are : " + str(res))
```

**Output:**

```
The original list is : ['GeeksforGeeks', 'Geeky', 'Computers', 'Algorithms']
All strings with given substring are : ['GeeksforGeeks', 'Geeky']

```

**方法三:使用`re + search()`**
正则表达式可以在 python 中执行很多任务。为了执行这个特殊的任务，正则表达式也可以派上用场。它使用`search()`找到所有匹配的子串并返回结果。

```
# Python code to demonstrate 
# to find strings with substrings 
# using re + search()
import re

# initializing list 
test_list = ['GeeksforGeeks', 'Geeky', 'Computers', 'Algorithms']

# printing original list 
print ("The original list is : " + str(test_list))

# initializing substring
subs = 'Geek'

# using re + search()
# to get string with substring 
res = [x for x in test_list if re.search(subs, x)]

# printing result 
print ("All strings with given substring are : " + str(res))
```

**Output:**

```
The original list is : ['GeeksforGeeks', 'Geeky', 'Computers', 'Algorithms']
All strings with given substring are : ['GeeksforGeeks', 'Geeky']

```