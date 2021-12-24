# Python |在特定索引处添加子串

> 原文:[https://www . geesforgeks . org/python-add-substring-at-specific-index/](https://www.geeksforgeeks.org/python-add-substring-at-specific-index/)

在 Python 中，字符串是不可变的数据类型，这意味着当一个人处理它的操作时有很多限制。如果没有列表重建，在字符串的某个位置添加一些东西是不可能的。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表切片**

这个任务可以使用列表切片来执行。在这种情况下，我们只是将列表分成两部分，在目标位置断开，然后在中间插入目标子串后重新连接。

```py
# Python3 code to demonstrate
# Add substring at specific index
# using list slicing

# initializing string
test_string = 'geeksgeeks'

# initializing add_string
add_string = "for"

# printing original string  
print("The original string : " + test_string)

# printing add string  
print("The add string : " + add_string)

# initializing N 
N = 5

# using list slicing
# Add substring at specific index 
res = test_string[ : N] + add_string + test_string[N : ]

# print result
print("The string after performing addition : " + str(res))
```

**Output :**

```py
The original string : geeksgeeks
The add string : for
The string after performing addition : geeksforgeeks

```

**方法 2:使用`join() + list() + insert()`**

针对以下问题，可以在中执行的另一种可能的黑客攻击是，将字符串转换为列表，然后在特定位置添加字符串，然后执行联接。

```py
# Python3 code to demonstrate
# Add substring at specific index
# using join() + list() + insert()

# initializing string
test_string = 'geeksgeeks'

# initializing add_string
add_string = "for"

# printing original string  
print("The original string : " + test_string)

# printing add string  
print("The add string : " + add_string)

# initializing N 
N = 5

# using join() + list() + insert()
# Add substring at specific index 
res = list(test_string)
res.insert(N, add_string)
res = ''.join(res)

# print result
print("The string after performing addition : " + str(res))
```

**Output :**

```py
The original string : geeksgeeks
The add string : for
The string after performing addition : geeksforgeeks

```