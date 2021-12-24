# Python |将字符串转换为字节

> 原文:[https://www . geesforgeks . org/python-convert-string-to-bytes/](https://www.geeksforgeeks.org/python-convert-string-to-bytes/)

像往常一样，内部转换非常流行，但是字符串到字节的转换现在更常见，因为为了处理文件或机器学习(Pickle 文件)，我们广泛地要求字符串转换成字节。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`bytes(str, enc)`**

可以使用通用字节函数将字符串转换为字节。该函数在内部指向 CPython 库，该库隐式调用编码函数将字符串转换为指定的编码。

```py
# Python code to demonstrate
# convert string to byte 
# Using bytes(str, enc)

# initializing string 
test_string = "GFG is best"

# printing original string 
print("The original string : " + str(test_string))

# Using bytes(str, enc)
# convert string to byte 
res = bytes(test_string, 'utf-8')

# print result
print("The byte converted string is  : " + str(res) + ", type : " + str(type(res)))
```

**Output :**

```py
The original string : GFG is best
The byte converted string is  : b'GFG is best', type : <class 'bytes'>

```

**方法 2:使用`encode(enc)`**

执行这一特定任务最推荐的方法是使用 encode 函数来完成转换，因为它减少了一个到特定库的额外链接，所以这个函数直接调用它。

```py
# Python code to demonstrate
# convert string to byte 
# Using encode(enc)

# initializing string 
test_string = "GFG is best"

# printing original string 
print("The original string : " + str(test_string))

# Using encode(enc)
# convert string to byte 
res = test_string.encode('utf-8')

# print result
print("The byte converted string is  : " + str(res) + ", type : " + str(type(res)))
```

**Output :**

```py
The original string : GFG is best
The byte converted string is  : b'GFG is best', type : <class 'bytes'>

```