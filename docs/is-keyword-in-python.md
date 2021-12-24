# 是 Python 中的关键字

> 原文:[https://www.geeksforgeeks.org/is-keyword-in-python/](https://www.geeksforgeeks.org/is-keyword-in-python/)

在编程中，关键字是语言的“保留词”，它向解释者传达特殊的含义。它可以是命令或参数。关键字不能在程序段中用作变量名。Python 语言也保留了一些传达特殊含义的关键词。在 Python 中，关键字区分大小写。

## 是关键字

此关键字用于测试对象身份。“is 关键字”用于测试两个变量是否属于同一个对象。如果两个对象相同，测试将返回`True`，否则即使两个对象 100%相等，测试也将返回“假”。

**注意:**操作符 `==` 用于测试两个物体是否相同。

**语法:**

```py
a is b

# Using if statement
if a is b:
    statement(s)
```

**例 1:**

```py
# Python program to demonstrate
# is keyword

x = ["a", "b", "c", "d"]

y =  ["a", "b", "c", "d"]

print(x is y)
print(x == y)
```

**输出:**
`False
True`

**例 2:**

```py
# Python program to demonstrate
# is keyword

x = 10
y = 10

if x is y:
    print(True)
else:
    print(False)
```

**输出:**

```py
True
```