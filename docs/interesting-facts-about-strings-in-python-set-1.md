# Python 中字符串的有趣事实|第 1 集

> 原文:[https://www . geesforgeks . org/interest-facts-about-strings-in-python-set-1/](https://www.geeksforgeeks.org/interesting-facts-about-strings-in-python-set-1/)

**1。字符串是不可变的**
一旦定义了字符串，就不能更改。

```
# Python3 program to show that 
# string cannot be changed

a = 'Geeks'

# output is displayed
print(a)

a[2] = 'E'
print(a) # causes error
```

输出:

```
Traceback (most recent call last):
  File "/home/adda662df52071c1e472261a1249d4a1.py", line 9, in 
    a[2] = 'E'
TypeError: 'str' object does not support item assignment
```

但是下面的代码可以正常工作。

```
# Python3 program to show that 
# a string can be appended to a string.

a = 'Geeks'

# output is displayed
print(a)
a = a + 'for'

print(a) # works fine
```

输出:

```
Geeks
Geeksfor
```

在第二个程序中，解释器复制原始字符串，然后对其进行处理和修改。因此表达式**a = a+‘for’**不会改变字符串，而是将变量 **a** 重新分配给由结果生成的新字符串，并删除之前的字符串。

了解使用 [id()](https://www.geeksforgeeks.org/id-function-python/) 功能。
id()函数用于返回对象的标识。

```
# Python3 program to show that
# both string hold same identity

string1 = "Hello"
string2 = "Hello"

print(id(string1))
print(id(string2))
```

输出:

```
93226944
93226944
```

string1 和 string2 都指向同一对象或同一位置。现在如果有人试图修改任何一个字符串结果都会不同。

```
# Modifying a string

string1 = "Hello"

# identity of string1
print(id(string1))

string1 += "World"
print(string1)

# identity of modified string1
print(id(string1))
```

输出:

```
93226944
'HelloWorld'
93326432
```

String1 被修改，这与字符串不可变的事实相矛盾，但是修改前后的标识是不同的。这意味着 string1 的新对象是在修改后创建的，这证实了字符串是不可变的，因为 string1 的前一个对象没有发生变化，而是创建了一个新的对象。

**2。创建字符串的三种方法:**
Python 中的字符串可以使用单引号、双引号或三引号来创建。

单引号和双引号同样适用于字符串创建。说到三重引号，当我们必须在多行中写一个字符串并按原样打印而不使用任何转义序列时，就会用到它们。

```
# Python3 program to create  
# strings in three different
# ways and concatenate them.

# string with single quotes
a = 'Geeks'

# string with double quotes
b = "for"

# string with triple quotes
c = '''Geeks a portal 
for geeks'''

d = '''He said, "I'm fine."'''

print(a)
print(b)
print(c)
print(d)

# Concatenation of strings created 
# using different quotes
print(a + b + c) 
```

输出:

```
Geeks
for
Geeks a portal 
for geeks
He said, "I'm fine."
GeeksforGeeks a portal 
for geeks
```

**如何在屏幕上打印单引号或双引号？**
我们可以通过以下两种方式做到这一点:

*   第一种是使用转义符来显示附加引号。
*   第二种方法是使用混合引号，即当我们想要打印单引号时，使用双引号作为分隔符，反之亦然。

示例-

```
print("Hi Mr Geek.")

# use of escape sequence
print("He said, \"Welcome to GeeksforGeeks\"")    

print('Hey so happy to be here')

# use of mix quotes
print ('Getting Geeky, "Loving it"')                
```

输出:

```
Hi Mr Geek.
He said, "Welcome to GeeksforGeeks"
Hey so happy to be here
Getting Geeky, "Loving it"
```

**如何改为打印转义字符？**

如果需要打印转义字符(\)，那么如果用户在字符串解释器中提到它，它将被认为是转义字符，并且不会打印它。为了打印转义字符，用户必须在**\ '**之前使用转义字符，如示例所示。

```
# Print Escape character
print (" \\ is back slash ")
```

输出:

```
 \ is back slash
```

本文由 **Arpit Agarwal** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论