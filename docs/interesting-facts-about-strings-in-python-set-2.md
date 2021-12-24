# Python 中字符串的有趣事实|集合 2(切片)

> 原文:[https://www . geesforgeks . org/interest-facts-about-strings-in-python-set-2/](https://www.geeksforgeeks.org/interesting-facts-about-strings-in-python-set-2/)

[Python 中字符串的有趣事实-第 1 集](https://www.geeksforgeeks.org/interesting-facts-about-strings-in-python-set-1/)

像其他编程语言一样，可以通过使用类似数组的索引语法来访问字符串中的单个字符。在这种情况下，我们可以通过索引号访问字符串的每个元素，索引从 0 开始。Python 进行索引越界检查。

因此，我们可以使用语法获得所需的字符，**string _ name[index _ position]**:

*   正 index_position 表示从起点(0)开始的元素，负 index 表示从终点(-1)开始的索引。

**例:**

```
# A python program to illustrate slicing in strings 

x = "Geeks at work"

# Prints 3rd character beginning from 0 
print (x[2]) 

# Prints 7th character 
print (x[6]) 

# Prints 3rd character from the rear beginning from -1 
print (x[-3]) 

# Length of string is 10 so it is out of bound 
print (x[15]) 
```

**输出:**

```
Traceback (most recent call last):
  File "8a33ebbf716678c881331d75e0b85fe6.py", line 15, in <module>
    print x[15] 
IndexError: string index out of range
```

```
e
a
o
```

**切片**

要从整个字符串中提取子字符串，我们使用类似

```
string_name[beginning: end : step]
```

*   Syntax, starting to represent the starting index of the string.
*   The end of indicates the end index of the string, excluding
*   Step indicates the distance between two words.

注意:我们也可以使用开始和仅和 ***步骤对字符串进行切片，这是可选的。**T3】*

**例:**

```
# A python program to illustrate 
# print substrings of a string 
x = "Welcome to GeeksforGeeks"

# Prints substring from 2nd to 5th character 
print (x[2:5])     

# Prints substring stepping up 2nd character 
# from 4th to 10th character 
print (x[4:10:2])     

# Prints 3rd character from rear from 3 to 5 
print (x[-5:-3])       
```

输出:

```
lco
oet
Ge
```

本文由 **Arpit Agarwal 供稿。**如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论