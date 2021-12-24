# 将字符串转换为 Python 中的 Set

> 原文:[https://www . geesforgeks . org/convert-string-to-set-in-python/](https://www.geeksforgeeks.org/convert-string-to-set-in-python/)

我们可以使用 [set()](https://www.geeksforgeeks.org/python-set-method/) 函数将字符串转换为 Python 中的 setin。

> **语法:**集合(可迭代)
> 
> **参数:**任何可重复序列，如列表、元组或字典。
> 
> **如果没有传递任何元素，则返回:**空集合。作为参数传递的可迭代修改的非重复元素。

**例 1 :**

```
# create a string str
string = "geeks"
print("Initially")
print("The datatype of string : " + str(type(string)))
print("Contents of string : " + string)

# convert String to Set
string = set(string)
print("\nAfter the conversion")
print("The datatype of string : " + str(type(string)))
print("Contents of string : ", string)
```

**输出:**

```
Initially
The datatype of string : 
Contents of string : geeks

After the conversion
The datatype of string : 
Contents of string :  {'k', 's', 'g', 'e'}

```

**例 2 :**

```
# create a string str
string = "Hello World!"
print("Initially")
print("The datatype of string : " + str(type(string)))
print("Contents of string : " + string)

# convert String to Set
string = set(string)
print("\nAfter the conversion")
print("The datatype of string : " + str(type(string)))
print("Contents of string : ", string)
```

**输出:**

```
Initially
The datatype of string : 
Contents of string : Hello World!

After the conversion
The datatype of string : 
Contents of string :  {'r', 'H', ' ', 'l', 'o', '!', 'd', 'W', 'e'}

```