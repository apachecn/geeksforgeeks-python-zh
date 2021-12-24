# Python 中的字典方法|集合 1 (cmp()，len()，items()…)

> 原文:[https://www . geesforgeks . org/dictionary-methods-in-python-set-1-CMP-len-items/](https://www.geeksforgeeks.org/dictionary-methods-in-python-set-1-cmp-len-items/)

下面的文章已经讨论了 Python 字典基础

[词典](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/)

本文讨论了一些词典方法。

**1。str(dic)** :-该方法用于**返回字符串**，用值表示所有的字典键。

**2。items()** :-此方法用于**返回列表**，所有字典键都有值。

```
# Python code to demonstrate working of
# str() and items()

# Initializing dictionary
dic = { 'Name' : 'Nandini', 'Age' : 19 }

# using str() to display dic as string
print ("The constituents of dictionary as string are : ")
print (str(dic))

# using str() to display dic as list
print ("The constituents of dictionary as list are : ")
print (dic.items())
```

输出:

```
The constituents of dictionary as string are : 
{'Name': 'Nandini', 'Age': 19}
The constituents of dictionary as list are : 
dict_items([('Name', 'Nandini'), ('Age', 19)])

```

**3。len()** :-返回字典元素的关键实体的**计数。**

**4。type()** :-此函数**返回参数的数据类型**。

```
# Python code to demonstrate working of
# len() and type()

# Initializing dictionary
dic = { 'Name' : 'Nandini', 'Age' : 19, 'ID' : 2541997 }

# Initializing list
li = [ 1, 3, 5, 6 ]

# using len() to display dic size
print ("The size of dic is : ",end="")
print (len(dic))

# using type() to display data type
print ("The data type of dic is : ",end="")
print (type(dic))

# using type() to display data type
print ("The data type of li is : ",end="")
print (type(li))
```

输出:

```
The size of dic is : 3
The data type of dic is : 
The data type of li is : 

```

**5。copy()** :-该功能将字典的**浅拷贝创建到其他字典中。**

**6。清除()** :-该功能用于**清除词典**内容。

```
# Python code to demonstrate working of
# clear() and copy()

# Initializing dictionary
dic1 = { 'Name' : 'Nandini', 'Age' : 19 }

# Initializing dictionary 
dic3 = {}

# using copy() to make shallow copy of dictionary
dic3 = dic1.copy()

# printing new dictionary
print ("The new copied dictionary is : ")
print (dic3.items())

# clearing the dictionary
dic1.clear()

# printing cleared dictionary
print ("The contents of deleted dictionary is : ",end="")
print (dic1.items())
```

输出:

```
The new copied dictionary is : 
dict_items([('Age', 19), ('Name', 'Nandini')])
The contents of deleted dictionary is : dict_items([])

```

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。