# Python 字典清除()

> 原文:[https://www.geeksforgeeks.org/python-dictionary-clear/](https://www.geeksforgeeks.org/python-dictionary-clear/)

clear()方法从字典中移除所有项目。

**语法:**

```
dict.clear()

```

**参数:**

```
The clear() method doesn't take any parameters.

```

**返回:**

```
The clear() method doesn't return any value.

```

**示例:**

```
Input : d = {1: "geeks", 2: "for"}
        d.clear()
Output : d = {}

```

**错误:**

```
As we are not passing any parameters there
is no chance for any error.

```

```
# Python program to demonstrate working of
# dictionary clear()
text = {1: "geeks", 2: "for"}

text.clear()
print('text =', text)
```

**输出:**

```
text = {}

```

**和给字典分配{}有什么不同？**
请参考下面的代码来看看区别。当我们将{}分配给字典时，会创建一个新的空字典并将其分配给引用。但是当我们清除了一个字典引用时，实际的字典内容就被删除了，所以所有引用字典的引用都变成了空的。

```
# Python code to demonstrate difference
# clear and {}.

text1 = {1: "geeks", 2: "for"}
text2 = text1

# Using clear makes both text1 and text2
# empty.
text1.clear()

print('After removing items using clear()')
print('text1 =', text1)
print('text2 =', text2)

text1 = {1: "one", 2: "two"}
text2 = text1

# This makes only text1 empty.
text1 = {}

print('After removing items by assigning {}')
print('text1 =', text1)
print('text2 =', text2)
```

输出:

```
After removing items using clear()
text1 = {}
text2 = {}
After removing items by assigning {}
text1 = {}
text2 = {1: 'one', 2: 'two'}

```