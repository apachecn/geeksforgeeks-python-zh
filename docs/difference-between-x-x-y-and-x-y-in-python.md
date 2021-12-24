# Python 中 x = x + y 和 x += y 的区别

> 原文:[https://www . geesforgeks . org/python 中-x-x-y-和-x-y-y-的区别/](https://www.geeksforgeeks.org/difference-between-x-x-y-and-x-y-in-python/)

我们经常用 **`x += y`** 代替 **`x = x + y`** 。那么，它们是相同的还是不同的呢？让我们在这里找到它。

**例 1:**

```py
x = [1, 2]
another_x = x
y = [3]

x += y

print(x)
print(another_x)
```

**输出:**

```py
[1, 2, 3]
[1, 2, 3]
```

**例 2:**

```py
x = [1, 2]
another_x = x
y = [3]

x = x + y

print(x)
print(another_x)
```

**输出:**

```py
[1, 2, 3]
[1, 2]
```

因此，我们发现这两个代码几乎相似，但输出仍然存在差异。因此，这背后的原因是，对于许多类型的对象， `x += y` 将就地修改 `x`所引用的对象，而 `x = x + y` 将创建一个新的对象并将 `x`重新分配给它。如果你仍然在某个地方有另一个对物体的引用，这种区别是很重要的，就像在这种情况下`another_a`是对物体的另一个引用。

然而，许多对象，如数字和字符串是“不可变的”——它们不能被就地修改——对于这些对象，`x += y`和`x = x + y`通常会做完全相同的事情。但是如果你编写自己的类，你可以定制`+`和`+=`在与该类的对象一起使用时做什么，如果你真的想的话，你可以让它们做完全不同的事情。

**例 3:**

```py
x = "12345"
another_x = x
y = "67890"

x += y

print(x)
print(another_x)
```

**输出:**

```py
1234567890
12345
```

**例 4:**

```py
x = "12345"
another_x = x
y = "67890"

x = x + y

print(x)
print(another_x)
```

**输出:**

```py
1234567890
12345
```