# Py-Facts–关于 Python 的 10 个有趣的事实

> 原文:[https://www . geesforgeks . org/py-facts-10-有趣-facts-about-python/](https://www.geeksforgeeks.org/py-facts-10-interesting-facts-about-python/)

Python 是当今最流行的编程语言之一，因为它的代码可读性和简单性。这都要感谢它的创造者吉多·范·罗瑟姆。

我用 Python 语言汇编了一个 10 个有趣事实的列表。它们是:
**1。**实际上有一首蒂姆·皮特斯写的诗，名叫《蟒蛇的禅》，只需在解释器中写下 import 就可以读懂。

## 计算机编程语言

```py
# Try to guess the result before you actually run it
import this
```

输出:

```py
The Zen of Python, by Tim Peters
Beautiful is better than ugly.

Explicit is better than implicit.

Simple is better than complex.

Complex is better than complicated.

Flat is better than nested.

Sparse is better than dense.

Readability counts.

Special cases aren't special enough to break the rules.

Although practicality beats purity.

Errors should never pass silently.

Unless explicitly silenced.

In the face of ambiguity, refuse the temptation to guess.

There should be one-- and preferably only one --obvious way to do it.

Although that way may not be obvious at first unless you're Dutch.

Now is better than never.

Although never is often better than *right* now.

If the implementation is hard to explain, it's a bad idea.

If the implementation is easy to explain, it may be a good idea.

Namespaces are one honking great idea -- let's do more of those!
```

**2。**在 Python 中可以返回多个值。不相信？参见下面的代码片段:

## 计算机编程语言

```py
# Multiple Return Values in Python!
def func():
   return 1, 2, 3, 4, 5

one, two, three, four, five = func()

print(one, two, three, four, five)
```

输出:

```py
(1, 2, 3, 4, 5)
```

**3。**可以在 Python 中使用带有“for”循环的“else”子句。这是一种特殊类型的语法，只有当 for 循环自然退出时才执行，没有任何 break 语句。

## 计算机编程语言

```py
def func(array):
     for num in array:
        if num%2==0:
            print(num)
            break # Case1: Break is called, so 'else' wouldn't be executed.
     else: # Case 2: 'else' executed since break is not called
        print("No call for Break. Else is executed")

print("1st Case:")
a = [2]
func(a)
print("2nd Case:")
a = [1]
func(a)
```

输出:

```py
1st Case:

2

2nd Case:

No call for Break. Else is executed
```

**4。**在 Python 中，一切都是通过引用来完成的。它不支持指针。

**5。**函数参数解包是 Python 的另一个令人敬畏的特性。可以分别使用*和**将列表或字典解包为函数参数。这通常被称为 Splat 运算符。此处示例

## 计算机编程语言

```py
def point(x, y):
    print(x,y)

foo_list = (3, 4)
bar_dict = {'y': 3, 'x': 2}

point(*foo_list) # Unpacking Lists
point(**bar_dict) # Unpacking Dictionaries
```

输出:

```py
3 4

2 3
```

**6。**想在 for 循环中找到索引吗？用“enumerate”包装一个 iterable，它将生成该项及其索引。请参见这段代码片段

## 计算机编程语言

```py
# Know the index faster
vowels=['a','e','i','o','u']
for i, letter in enumerate(vowels):
    print (i, letter)
```

输出:

```py
(0, 'a')

(1, 'e')

(2, 'i')

(3, 'o')

(4, 'u')
```

**7。**一个可以在 Python 中链式比较的运算符答案= 1 < x < 10 在 Python 中是可执行的。这里有更多的例子

## 计算机编程语言

```py
# Chaining Comparison Operators
i = 5;

ans = 1 < i < 10
print(ans)

ans = 10 > i <= 9
print(ans)

ans = 5 == i
print(ans)
```

输出:

```py
True

True

True
```

**8。**我们不能定义英菲尼迪对吗？但是等等！不适合 Python。看到这个惊人的例子

## 计算机编程语言

```py
# Positive Infinity
p_infinity = float('Inf')

if 99999999999999 > p_infinity:
    print("The number is greater than Infinity!")
else:
    print("Infinity is greatest")

# Negative Infinity
n_infinity = float('-Inf')
if -99999999999999 < n_infinity:
    print("The number is lesser than Negative Infinity!")
else:
    print("Negative Infinity is least")
```

输出:

```py
Infinity is greatest

Negative Infinity is least
```

**9。**不用循环构建列表，可以用列表理解更简洁地构建。请参阅此代码了解更多信息。

## 计算机编程语言

```py
# Simple List Append
a = []
for x in range(0,10):
    a.append(x)
print(a)

# List Comprehension
print([x for x in a])
```

输出:

```py
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

**10。**最后是 Python 的特殊切片运算符。这是一种从列表中获取项目以及更改它们的方法。请参见这段代码片段

## 计算机编程语言

```py
# Slice Operator
a = [1,2,3,4,5]

print(a[0:2]) # Choose elements [0-2), upper-bound noninclusive

print(a[0:-1]) # Choose all but the last

print(a[::-1]) # Reverse the list

print(a[::2]) # Skip by 2

print(a[::-2]) # Skip by -2 from the back
```

输出:

```py
[1, 2]

[1, 2, 3, 4]

[5, 4, 3, 2, 1]

[1, 3, 5]

[5, 3, 1]
```

本文由**哈什特·古普塔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如发现任何不正确的地方，请写评论，或者您想分享更多关于上述话题的信息