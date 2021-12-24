# Python 中的 id()函数

> 原文:[https://www.geeksforgeeks.org/id-function-python/](https://www.geeksforgeeks.org/id-function-python/)

**简介**
id()是 Python 中的一个内置函数。
**语法:**

```py
id(object)
```

如我们所见，该函数接受单个参数，并用于返回对象的标识。**这个身份必须是唯一的，并且在这个对象的一生中是不变的。**生命周期不重叠的两个对象可能具有相同的 id()值。如果我们把它和 C 联系起来，那么它们实际上是内存地址，在 Python 中，这是唯一的 id。这个函数一般在 Python 内部使用。

示例:

```py
The output is the identity of the 
object passed. This is random but 
when running in the same program, 
it generates unique and same identity. 

Input : id(1025)
Output : 140365829447504
Output varies with different runs

Input : id("geek")
Output : 139793848214784

```

```py
# This program shows various identities
str1 = "geek"
print(id(str1))

str2 = "geek"
print(id(str2))

# This will return True
print(id(str1) == id(str2))

# Use in Lists
list1 = ["aakash", "priya", "abdul"]
print(id(list1[0]))
print(id(list1[2]))

# This returns false
print(id(list1[0])==id(list1[2]))
```

输出:

```py
140252505691448
140252505691448
True
140252505691840
140252505739928
False

```