# 收藏。Python 中的用户字符串

> 原文:[https://www . geesforgeks . org/collections-user string-in-python/](https://www.geeksforgeeks.org/collections-userstring-in-python/)

**字符串**是代表 Unicode 字符的字节数组。但是，Python 不支持字符数据类型。字符是长度为 1 的字符串。
T3】例:

## 蟒蛇 3

```py
# Python program to demonstrate
# string

# Creating a String 
# with single Quotes
String1 = 'Welcome to the Geeks World'
print("String with the use of Single Quotes: ")
print(String1)

# Creating a String
# with double Quotes
String1 = "I'm a Geek"
print("\nString with the use of Double Quotes: ")
print(String1)
```

**输出:**

```py
String with the use of Single Quotes: 
Welcome to the Geeks World

String with the use of Double Quotes: 
I'm a Geek
```

**注:**更多信息请参考[蟒串](http://geeksforgeeks.org/python-strings/)T4】

## 收藏品。用户字符串

Python 支持一个[字符串](http://geeksforgeeks.org/python-strings/)，就像集合模块中的一个名为**用户字符串**的容器。这个类充当字符串对象的包装类。当一个人想要创建一个自己的带有一些修改的功能或一些新功能的字符串时，这个类是有用的。它可以被认为是为字符串添加新行为的一种方式。这个类接受任何可以转换成字符串的参数，并模拟一个内容保存在常规字符串中的字符串。该字符串可由该类的数据属性访问。
**语法:**

```py
collections.UserString(seq)
```

**例 1:**

## 蟒蛇 3

```py
# Python program to demonstrate
# userstring

from collections import UserString

d = 12344

# Creating an UserDict
userS = UserString(d)
print(userS.data)

# Creating an empty UserDict
userS = UserString("")
print(userS.data)
```

**输出:**

```py
12344
```

**例 2:**

## 蟒蛇 3

```py
# Python program to demonstrate
# userstring

from collections import UserString

# Creating a Mutable String
class Mystring(UserString):

    # Function to append to
    # string
    def append(self, s):
        self.data += s

    # Function to remove from
    # string
    def remove(self, s):
        self.data = self.data.replace(s, "")

# Driver's code
s1 = Mystring("Geeks")
print("Original String:", s1.data)

# Appending to string
s1.append("s")
print("String After Appending:", s1.data)

# Removing from string
s1.remove("e")
print("String after Removing:", s1.data)
```

**输出:**

```py
Original String: Geeks
String After Appending: Geekss
String after Removing: Gkss
```