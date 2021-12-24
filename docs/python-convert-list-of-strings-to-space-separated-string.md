# Python |将字符串列表转换为空格分隔的字符串

> 原文:[https://www . geesforgeks . org/python-convert-list-string-to-space-separated-string/](https://www.geeksforgeeks.org/python-convert-list-of-strings-to-space-separated-string/)

给定一个字符串列表，编写一个 Python 程序将给定的字符串列表转换成一个用空格分隔的字符串。

**示例:**

```
Input : ['geeks', 'for', 'geeks']
Output : geeks for geeks

Input : ['Python', 'Language']
Output : Python Language

```

**进场#1 :** 蟒蛇串*翻译()*

string translate()方法返回一个字符串，其中每个字符都映射到翻译表中相应的字符。这种方法的局限性是不适用于 Python 3 及以上版本。

```
# Python3 program to Convert a list of 
# strings to space-separated string

def convert(lst):

    return str(lst).translate(None, '[],\'')

# Driver code
lst = ['geeks', 'for', 'geeks']
print(convert(lst))
```

**Output:**

```
geeks for geeks

```

**方法#2 :** *join()* 函数
join()方法是一个字符串方法，返回一个字符串，其中序列的元素已经通过字符串分隔符连接在一起。在这种方法中，空间是分隔符。

```
# Python3 program to Convert list of 
# strings to space separated string

def convert(lst):

    return ' '.join(lst)

# Driver code
lst = ['geeks', 'for', 'geeks']
print(convert(lst))
```

**Output:**

```
geeks for geeks

```