# python 中的循环

> 原文:[https://www.geeksforgeeks.org/loops-in-python/](https://www.geeksforgeeks.org/loops-in-python/)

Python 编程语言提供了以下类型的循环来处理循环需求。Python 提供了三种执行循环的方法。虽然所有的方法都提供类似的基本功能，但是它们的语法和条件检查时间不同。

1.  **While Loop:**
2.  在 python 中，while 循环用于重复执行一个语句块，直到满足给定的条件。当条件变为假时，执行程序中紧接着循环的那一行。

**语法**:

```py
while expression:
    statement(s)

```

3.编程构造后缩进相同数量字符空间的所有语句都被视为单个代码块的一部分。Python 使用缩进作为其对语句进行分组的方法。
例:

## 计算机编程语言

```py
# Python program to illustrate
# while loop
count = 0
while (count < 3):   
    count = count + 1
    print("Hello Geek")
```

**输出:**

```py
Hello Geek
Hello Geek
Hello Geek

```

*   **将 else 语句与 while 循环一起使用:**如上所述，while 循环执行该块，直到满足某个条件。当条件变为假时，循环后立即执行语句。
    else 子句仅在 while 条件变为 false 时执行。如果脱离循环，或者引发异常，它将不会被执行。
    **如果不是这样:**

## 计算机编程语言

```py
if condition:
    # execute these statements
else:
    # execute these statements
```

*   **而像这样的循环是相似的**

## 计算机编程语言

```py
while condition:
     # execute these statements
else:
     # execute these statements
```

## 计算机编程语言

```py
#Python program to illustrate
# combining else with while
count = 0
while (count < 3):   
    count = count + 1
    print("Hello Geek")
else:
    print("In Else Block")
```

**输出:**

```py
Hello Geek
Hello Geek
Hello Geek
In Else Block

```

*   **单语句 while 块:**就像 if 块一样，如果 while 块由单个语句组成，我们可以在一行中声明整个循环，如下所示:

## 计算机编程语言

```py
# Python program to illustrate
# Single statement while block
count = 0
while (count == 0): print("Hello Geek")
```

*   **注意**:建议**不要使用**这种类型的循环，因为这是一个永不结束的无限循环，条件总是真的，你必须强制终止编译器。

1.  **For in Loop:**For Loop 用于顺序遍历。例如:遍历列表、字符串或数组等。Python 中没有循环的 C 风格，即 for(I = 0；一<n；i++)。在其他语言中，每个循环都有一个类似于[的“for in”循环。让我们学习如何使用 in 循环进行顺序遍历。](https://www.geeksforgeeks.org/g-fact-40-foreach-in-c-and-java/)

**语法:**

```py
for iterator_var in sequence:
    statements(s)

```

它可以用来迭代一个范围和迭代器。

## 蟒蛇 3

```py
# Python program to illustrate
# Iterating over range 0 to n-1

n = 4
for i in range(0, n):
    print(i)
```

**输出:**

```py
0
1
2
3

```

## 计算机编程语言

```py
# Python program to illustrate
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

**输出:**

```py
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

**按序列索引迭代**:我们也可以用序列中元素的索引进行迭代。关键思想是首先计算列表的长度，然后在这个长度范围内迭代序列。
见下例:

## 计算机编程语言

```py
# Python program to illustrate
# Iterating by index

list = ["geeks", "for", "geeks"]
for index in range(len(list)):
    print list[index]
```

**输出:**

```py
geeks
for
geeks

```

**将 else 语句与 for 循环结合使用:**我们还可以将 else 语句与 for 循环结合使用，就像在 while 循环中一样。但是由于 for 循环中没有终止执行的条件，因此 else 块将在 for 块完成执行后立即执行。
下面的例子解释了如何做到这一点:

## 计算机编程语言

```py
# Python program to illustrate
# combining else with for

list = ["geeks", "for", "geeks"]
for index in range(len(list)):
    print list[index]
else:
    print "Inside Else Block"
```

**输出:**

```py
geeks
for
geeks
Inside Else Block

```

**嵌套循环:** Python 编程语言允许在另一个循环中使用一个循环。下面的部分展示了几个例子来说明这个概念。
语法:

## 计算机编程语言

```py
for iterator_var in sequence:
    for iterator_var in sequence:
        statements(s)
        statements(s)
```

Python 编程语言中嵌套 while 循环语句的语法如下:

## 计算机编程语言

```py
while expression:
    while expression:
        statement(s)
        statement(s)
```

关于循环嵌套的最后一点是，我们可以将任何类型的循环放入任何其他类型的循环中。例如，For 循环可以在 while 循环内部，反之亦然。

## 计算机编程语言

```py
# Python program to illustrate
# nested for loops in Python
from __future__ import print_function
for i in range(1, 5):
    for j in range(i):
         print(i, end=' ')
    print()
```

**输出:**

```py
1
2 2
3 3 3
4 4 4 4

```

**循环控制语句:**循环控制语句改变其正常顺序的执行。当执行离开一个范围时，在该范围内创建的所有自动对象都将被销毁。Python 支持以下控制语句。

*   **Continue 语句:**它将控制返回到循环的开始。

## 计算机编程语言

```py
# Prints all letters except 'e' and 's'
for letter in 'geeksforgeeks':
    if letter == 'e' or letter == 's':
         continue
    print 'Current Letter :', letter
    var = 10
```

**输出:**

```py
Current Letter : g
Current Letter : k
Current Letter : f
Current Letter : o
Current Letter : r
Current Letter : g
Current Letter : k

```

*   **中断语句:**它将控制带出循环

## 计算机编程语言

```py
for letter in 'geeksforgeeks':

    # break the loop as soon it sees 'e'
    # or 's'
    if letter == 'e' or letter == 's':
         break

print 'Current Letter :', letter
```

**输出:**

```py
Current Letter : e

```

*   **Pass 语句:**我们用 Pass 语句写空循环。Pass 也用于空的控制语句、函数和类。

## 计算机编程语言

```py
# An empty loop
for letter in 'geeksforgeeks':
    pass
print 'Last Letter :', letter
```

**输出:**

```py
Last Letter : s

```

**Python 中 for 循环内部是如何工作的？**

在继续本节之前，您应该对 Python 迭代器有一个预先的了解。

首先，让我们看看简单的 for 循环是什么样子的。

## 蟒蛇 3

```py
# A simple for loop example

fruits = ["apple", "orange", "kiwi"]

for fruit in fruits:

 print(fruit)
```

**Output**

```py
apple
orange
kiwi

```

在这里，我们可以看到 for 循环在一个可迭代的对象上迭代，该对象是一个列表。列表、集合、字典这些是很少的可迭代对象，而整数对象不是可迭代对象。

For 循环可以迭代任何可迭代对象(例如:列表、集合、字典、元组或字符串)。

现在在上面例子的帮助下，让我们深入并看看内部发生了什么。

1.  在 iter()函数的帮助下，使列表(iterable)成为可迭代对象。
2.  运行一个无限 while 循环，并且仅在引发 StopIteration 时中断。
3.  在 try 块中，我们使用 next()函数获取水果的下一个元素。
4.  获取元素后，我们对元素执行了操作。(即印刷品(水果))

## 蟒蛇 3

```py
fruits = ["apple", "orange", "kiwi"]

# Creating an iterator object
# from that iterable i.e fruits
iter_obj = iter(fruits)

# Infinite while loop
while True:
  try:

      # getting the next item
      fruit = next(iter_obj)
      print(fruit)
  except StopIteration:

      # if StopIteration is raised,
      # break from loop
       break
```

**Output**

```py
apple
orange
kiwi

```

我们可以看到，在引擎盖下，我们正在调用 iter()和 next()方法。

**练习:**如何使用 while 和 for 循环以相反的顺序(从最后一项到第一项)打印列表。
本文由**阿西瓦德·库马尔供稿。**如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如发现任何不正确的地方，或想分享更多关于上述话题的信息，请写评论