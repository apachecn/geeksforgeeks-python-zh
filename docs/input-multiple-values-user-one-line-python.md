# 如何在 Python 中一行输入用户的多个值？

> 原文:[https://www . geesforgeks . org/input-multi-values-user-one-line-python/](https://www.geeksforgeeks.org/input-multiple-values-user-one-line-python/)

例如，在 C 语言中，我们可以这样做:

```
// Reads two values in one line
scanf("%d %d", &x, &y) 
```

一种解决方案是使用 raw_input()两次。

```
x, y = input(),  input()
```

另一种解决方案是使用 [split()](https://www.geeksforgeeks.org/how-to-split-a-string-in-cc-python-and-java/)

```
x, y = input().split()
```

请注意，我们不必显式指定 split(')，因为 split()默认使用任何空白字符作为分隔符。

在上面的 Python 代码中需要注意的一点是，x 和 y 都是字符串。我们可以用另一行

```
x, y = [int(x), int(y)]

# We can also use  list comprehension
x, y = [int(x) for x in [x, y]]

```

将它们转换成 int

下面是完整的一行代码从标准输入中读取两个整数变量使用 split 和[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

```
# Reads two numbers from input and typecasts them to int using 
# list comprehension
x, y = [int(x) for x in input().split()]  
```

```
# Reads two numbers from input and typecasts them to int using 
# map function
x, y = map(int, input().split())
```

本文由 **Abhishek Shukla** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论