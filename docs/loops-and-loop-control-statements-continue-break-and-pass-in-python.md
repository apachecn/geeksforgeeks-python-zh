# Python 中的循环和控制语句(继续、中断和传递)

> 原文:[https://www . geesforgeks . org/loops-and-loop-control-statements-continue-break-and-pass-in-python/](https://www.geeksforgeeks.org/loops-and-loop-control-statements-continue-break-and-pass-in-python/)

Python 编程语言提供了以下类型的循环来处理循环需求。

<center>**While Loop**</center>

Syntax :

```
while expression:
    statement(s)

```

在 Python 中，编程构造后缩进相同数量字符空间的所有语句都被视为单个代码块的一部分。Python 使用缩进作为其对语句进行分组的方法。

```
# prints Hello Geek 3 Times
count = 0
while (count < 3):    
    count = count+1
    print("Hello Geek")
```

输出:

```
Hello Geek
Hello Geek
Hello Geek

```

关于 while 循环用于迭代器的例子，参见[这个](https://www.geeksforgeeks.org/using-iterations-in-python-effectively/)。正如文章中提到的，不建议在 python 中对迭代器使用 while 循环。

<center>**For in Loop**</center>

In Python, there is no C style for loop, i.e., for (i=0; i<n; i++). There is “for in” loop which is similar to [for each](https://www.geeksforgeeks.org/g-fact-40-foreach-in-c-and-java/) loop in other languages.

语法:

```
for iterator_var in sequence:
    statements(s)
```

它可以用来迭代迭代器和范围。

```
# Iterating over a list
print("List Iteration")
l = ["geeks", "for", "geeks"]
for i in l:
    print(i)

# Iterating over a tuple (immutable)
print("\nTuple Iteration")
t = ("geeks", "for", "geeks")
for i in t:
    print(i)

# Iterating over a String
print("\nString Iteration")    
s = "Geeks"
for i in s :
    print(i)

# Iterating over dictionary
print("\nDictionary Iteration")   
d = dict() 
d['xyz'] = 123
d['abc'] = 345
for i in d :
    print("%s  %d" %(i, d[i]))
```

输出:

```
List Iteration
geeks
for
geeks

Tuple Iteration
geeks
for
geeks

String Iteration
G
e
e
k
s

Dictionary Iteration
xyz  123
abc  345

```

我们可以为用户定义的迭代器使用 in 循环。详见[本](https://www.geeksforgeeks.org/iterators-in-python/)举例。

<center>**Nested Loops**</center>

Python programming language allows to use one loop inside another loop. Following section shows few examples to illustrate the concept.
Syntax:

```
for iterator_var in sequence:
    for iterator_var in sequence:
        statements(s)
        statements(s)

```

Python 编程语言中嵌套 while 循环语句的语法如下:

```
while expression:
    while expression: 
        statement(s)
        statement(s)

```

关于循环嵌套的最后一点是，我们可以将任何类型的循环放入任何其他类型的循环中。例如，For 循环可以在 while 循环内部，反之亦然。

```
from __future__ import print_function
for i in range(1, 5):
    for j in range(i):
         print(i, end=' ')
    print()
```

输出:

```
1
2 2
3 3 3
4 4 4 4
```

<center>**Loop Control Statements**</center>

Loop control statements change execution from its normal sequence. When execution leaves a scope, all automatic objects that were created in that scope are destroyed. Python supports the following control statements.

**继续语句**
它将控制返回到循环的开始。

```
# Prints all letters except 'e' and 's'
for letter in 'geeksforgeeks': 
    if letter == 'e' or letter == 's':
         continue
    print 'Current Letter :', letter
    var = 10
```

输出:

```
Current Letter : g
Current Letter : k
Current Letter : f
Current Letter : o
Current Letter : r
Current Letter : g
Current Letter : k

```

**中断声明**
它将控制带出循环

```
for letter in 'geeksforgeeks': 

    # break the loop as soon it sees 'e' 
    # or 's'
    if letter == 'e' or letter == 's':
         break

print 'Current Letter :', letter
```

输出:

```
Current Letter : e
```

**Pass 语句**
我们用 Pass 语句写空循环。Pass 也用于空的控制语句、函数和类。

```
# An empty loop
for letter in 'geeksforgeeks':
    pass
print 'Last Letter :', letter
```

输出:

```
Last Letter : s
```

**练习:**
如何使用 while 和 for 循环以相反的顺序(从最后一项到第一项)打印列表。

本文由**阿西瓦德·库马尔供稿。**如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上述话题的信息，请写评论