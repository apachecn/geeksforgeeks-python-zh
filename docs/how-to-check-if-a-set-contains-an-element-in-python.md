# 如何在 Python 中检查一个集合是否包含元素？

> 原文:[https://www . geesforgeks . org/如何检查集合是否包含 python 中的元素/](https://www.geeksforgeeks.org/how-to-check-if-a-set-contains-an-element-in-python/)

在本文中，我们将讨论如何在 python 中检查一个集合是否包含元素。

## 方法:1 在运算符中使用

这是一个成员运算符，用于检查给定值是否存在于集合中。如果给定元素存在于集合中，它将返回真，否则返回假。

**语法**:

```py
element in set
```

在哪里

*   集合是一个输入集合
*   元素是要检查的值

**示例:**检查集合中是否存在元素

## 蟒蛇 3

```py
# import random module
import random

# create a set with integer elements
data = {7058, 7059, 7072, 7074, 7076}

# check 7058
print(7058 in data)

# check 7059
print(7059 in data)

# check 7071
print(7071 in data)
```

**输出:**

```py
True
True
False
```

## 方法 2:不在运算符中使用

这是一个成员运算符，用于检查给定值是否存在于集合中。如果给定元素不在集合中，它将返回真，否则返回假

**语法**:

```py
element not in set
```

哪里，

*   集合是一个输入集合
*   元素是要检查的值

**示例**:检查集合中是否存在元素

## 蟒蛇 3

```py
# import random module
import random

# create a set with integer elements
data = {7058, 7059, 7072, 7074, 7076}

# check 7058
print(7058 not in data)

# check 7059
print(7059 not in data)

# check 7071
print(7071 not in data)
```

**输出:**

```py
False
False
True
```