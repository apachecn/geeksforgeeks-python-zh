# 使用乘法运算符

在 Python 中创建字符串的多个副本

> 原文:[https://www . geesforgeks . org/create-multiple-copy-in-a-string-in-python-by-use-乘法-operator/](https://www.geeksforgeeks.org/create-multiple-copies-of-a-string-in-python-by-using-multiplication-operator/)

在本文中，我们将看到如何使用乘法运算符(*)来创建字符串的多个副本。Python 支持对字符串执行某些操作，乘法运算符就是其中之一。

### 方法 1:

只需在要复制的字符串上使用乘法运算符，并达到所需的复制次数。

**语法**:

> **str2 = str1 * N**
> 
> 其中 str2 是要存储新字符串的新字符串
> 
> str1 是原始字符串
> 
> n 是您想要复制字符串的次数。
> 
> 使用乘法运算符后，我们得到一个字符串作为输出

**例 1:**

## 蟒蛇 3

```py
# Original string
a = "Geeks"

# Multiply the string and store
# it in a new string
b = a*3

# Display the strings
print(f"Original string is: {a}")
print(f"New string is: {b}")
```

**输出:**

> 原字符串为:极客
> 
> 新字符串是:极客极客极客

**例 2:**

## 蟒蛇 3

```py
# Initializing the original string
a = "Hello"
n = 5

# Multiplying the string
b = a*n

# Print the strings
print(f"Original string is: {a}")
print(f"New string is: {b}")
```

**输出:**

> 原字符串是:你好
> 
> 新字符串是:HelloHelloHelloHello

### 方法 2:在列表中多次复制给定的字符串

如果我们有一个字符串作为列表元素，并且我们在列表上使用乘法运算符，我们将得到一个包含相同元素的新列表，该列表被复制了指定的次数。

**语法:**

> **a =[“ST R1”]* N**
> 
> a 将是包含 N 次的列表。
> 
> 我们想要在列表中复制的元素不必是字符串。列表中的乘法运算符可以复制任何内容。

**例 3** :

## 蟒蛇 3

```py
# Initialize the list
a = ["Geeks"]

# Number of copies
n = 3

# Multiplying the list elements
b = a*n

# print the list
print(f"Original list is: {a} ")
print(f"List after multiplication is: {b}")
```

**输出:**

> 原始列表是:['极客']
> 
> 乘法后的列表是:['极客'，'极客'，'极客']

**例 4** :同样方法的简写方法

## 蟒蛇 3

```py
# initializing a string with all True's
a = [True]*5
print(a)

# Initializing a list with all 0
a = [0]*10
print(a)
```

**输出:**

> [真，真，真，真，真]
> 
> [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]