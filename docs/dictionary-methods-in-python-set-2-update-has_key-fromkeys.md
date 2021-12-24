# Python 中的字典方法|集合 2(更新()、has_key()、fromkeys()…)

> 原文:[https://www . geesforgeks . org/dictionary-methods-in-python-set-2-update-has _ key-from keys/](https://www.geeksforgeeks.org/dictionary-methods-in-python-set-2-update-has_key-fromkeys/)

下面的第 1 集讨论了一些字典方法

[Python 中的字典方法|集合 1 (cmp()，len()，items()…)](https://www.geeksforgeeks.org/dictionary-methods-in-python-set-1-cmp-len-items/)

本文将讨论更多方法。

**1。fromkeys(seq，value)** :-该方法用于从其参数中提到的序列中声明一个**新字典。这个函数也可以**用“值”参数**初始化声明的字典。**

**2。更新(dic)** :-该功能用于**更新字典添加其他字典键**。

```py
# Python code to demonstrate working of
# fromkeys() and update()

# Initializing dictionary 1
dic1 = { 'Name' : 'Nandini', 'Age' : 19 }

# Initializing dictionary 2
dic2 = { 'ID' : 2541997 }

# Initializing sequence
sequ = ('Name', 'Age', 'ID')

# using update to add dic2 values in dic 1
dic1.update(dic2)

# printing updated dictionary values
print ("The updated dictionary is : ")
print (str(dic1))

# using fromkeys() to transform sequence into dictionary
dict = dict.fromkeys(sequ,5)

# printing new dictionary values
print ("The new dictionary values are : ")
print (str(dict))
```

输出:

```py
The updated dictionary is : 
{'Age': 19, 'Name': 'Nandini', 'ID': 2541997}
The new dictionary values are : 
{'Age': 5, 'Name': 5, 'ID': 5}

```

**3。has_key()** :-如果字典中存在**指定的键**，则该函数返回 true，否则返回 false。

**4。get(key，def_val)** :-该函数返回与参数中提到的键关联的**键值。如果键不存在，则返回默认值。**

```py
# Python code to demonstrate working of
# has_key() and get()

# Initializing dictionary
dict = { 'Name' : 'Nandini', 'Age' : 19 }

# using has_key() to check if dic1 has a key
if dict.has_key('Name'):
       print ("Name is a key")
else : print ("Name is not a key")

# using get() to print a key value
print ("The value associated with ID is : ")
print (dict.get('ID', "Not Present"))

# printing dictionary values
print ("The dictionary values are : ")
print (str(dict))
```

输出:

```py
Name is a key
The value associated with ID is : 
Not Present
The dictionary values are : 
{'Name': 'Nandini', 'Age': 19}

```

**5。setdefault(key，def_value)** :-该功能还会**搜索一个 key** 并像 get()一样显示其值，但是如果 key 不存在，它会**用 def_value** 创建一个新的 key。

```py
# Python code to demonstrate working of
# setdefault()

# Initializing dictionary
dict = { 'Name' : 'Nandini', 'Age' : 19 }

# using setdefault() to print a key value
print ("The value associated with Age is : ",end="")
print (dict.setdefault('ID', "No ID"))

# printing dictionary values
print ("The dictionary values are : ")
print (str(dict))
```

输出:

```py
The value associated with Age is : No ID
The dictionary values are : 
{'Name': 'Nandini', 'Age': 19, 'ID': 'No ID'}

```

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。