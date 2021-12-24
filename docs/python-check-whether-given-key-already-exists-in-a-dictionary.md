# 检查给定的密钥是否已经存在于 Python 字典中

> 原文:[https://www . geesforgeks . org/python-check-给定密钥是否已经存在于字典中/](https://www.geeksforgeeks.org/python-check-whether-given-key-already-exists-in-a-dictionary/)

给定 Python 中的字典，编写一个 Python 程序来检查字典中是否已经存在给定的键。如果存在，打印“存在”和键值。否则打印“不存在”。

**示例:**

```
Input : {'a': 100, 'b':200, 'c':300}, key = b
Output : Present, value = 200

Input : {'x': 25, 'y':18, 'z':45}, key = w
Output : Not present

```

**方法#1 :** 使用内置方法`keys()`

`keys()`方法返回字典中所有可用键的列表。使用内置方法`keys()`，使用 if 语句和“in”运算符检查关键字是否存在于字典中。

```
# Python3 Program to check whether a 
# given key already exists in a dictionary.

# Function to print sum
def checkKey(dict, key):

    if key in dict.keys():
        print("Present, ", end =" ")
        print("value =", dict[key])
    else:
        print("Not present")

# Driver Code
dict = {'a': 100, 'b':200, 'c':300}

key = 'b'
checkKey(dict, key)

key = 'w'
checkKey(dict, key)
```

**输出:**

```
Present, value = 200
Not present

```

**接近#2 :** 使用`if`和`in`

该方法简单使用`if`语句检查字典中是否存在给定的键。

```
# Python3 Program to check whether a 
# given key already exists in a dictionary.

# Function to print sum
def checkKey(dict, key):

    if key in dict:
        print("Present, ", end =" ")
        print("value =", dict[key])
    else:
        print("Not present")

# Driver Code
dict = {'a': 100, 'b':200, 'c':300}

key = 'b'
checkKey(dict, key)

key = 'w'
checkKey(dict, key)
```

**输出:**

```
Present, value = 200
Not present

```

**方法 3 :** 使用内置方法`has_key()`

`has_key()`如果给定的键在字典中可用，则方法返回 true，否则返回 false。使用内置方法`has_key()`，使用 if 语句检查关键字是否存在于字典中。

**注–**`has_keys()`法已从 Python3 版本中移除。因此，它只能在 Python2 中使用。

```
# Python3 Program to check whether a 
# given key already exists in a dictionary.

# Function to print sum
def checkKey(dict, key):

    if dict.has_key(key):
        print "Present, value =", dict[key]
    else:
        print "Not present"

# Driver Function
dict = {'a': 100, 'b':200, 'c':300}
key = 'b'
checkKey(dict, key)

key = 'w'
checkKey(dict, key)
```

**输出:**

```
Present, value = 200
Not present

```