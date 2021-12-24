# Python |加入 unicode 列表元素

> 原文:[https://www . geeksforgeeks . org/python-join-unicode-list-elements/](https://www.geeksforgeeks.org/python-joining-unicode-list-elements/)

有时我们可以接收不同格式的数据，而不是传统的列表、字符串、整数或字符。Python 还有许多其他数据类型，处理它们的知识通常很有用。本文演示了列表中 unicode 字符的连接。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`join()` +列表理解**
在该方法中，我们首先将字符串的 unicode 元素转换为字符串元素，然后执行连接操作，从 unicode 元素列表中获取连接的结果字符串。仅适用于 Python2。

```
# Python code to demonstrate
# Joining unicode list elements
# using join() + list comprehension

# initializing list
test_list = [ 'We', 'love', 'Geeksforgeeks']
map(unicode, test_list)

# printing original list
print("The original list is : " + str(test_list))

# using join() + list comprehension to
# Join unicode list elements
res = b':'.join(str(i) for i in test_list)

# printing result
print ("The joined string is : " + res)
```

**Output :**

```
The original list is : ['We', 'love', 'Geeksforgeeks']
The joined string is : We:love:Geeksforgeeks

```