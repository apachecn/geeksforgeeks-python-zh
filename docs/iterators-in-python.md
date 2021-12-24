# Python 中的迭代器

> 原文:[https://www.geeksforgeeks.org/iterators-in-python/](https://www.geeksforgeeks.org/iterators-in-python/)

python 中的迭代器是一个对象，用于迭代列表、元组、字典和集合等可迭代对象。迭代器对象使用 **iter()** 方法初始化。它使用 **next()** 方法进行迭代。

1.  **__iter(iterable)__** 方法，用于初始化迭代器。这会返回一个迭代器对象
2.  **next(_ _ Python 3 中的 next _)**next 方法返回 iterable 的下一个值。当我们使用 for 循环遍历任何可迭代对象时，它在内部使用 iter()方法获得一个迭代器对象，该对象进一步使用 next()方法进行迭代。此方法引发一个停止迭代来表示迭代结束。

迭代器在 python 中是如何工作的

## 蟒蛇 3

```py
# Here is an example of a python inbuilt iterator
# value can be anything which can be iterate
iterable_value = 'Geeks'
iterable_obj = iter(iterable_value)

while True:
    try:

        # Iterate by calling next
        item = next(iterable_obj)
        print(item)
    except StopIteration:

        # exception will happen when iteration will over
        break
```

**输出:**

```py
G                                                                                                                                                                            
e                                                                                                                                                                            
e                                                                                                                                                                            
k                                                                                                                                                                            
s

```

下面是一个简单的 Python 自定义迭代器，它创建的迭代器类型从 10 迭代到给定的极限。例如，如果限制为 15，则打印 10 11 12 13 14 15。如果限制为 5，则不打印任何内容。

## 蟒蛇 3

```py
# A simple Python program to demonstrate
# working of iterators using an example type
# that iterates from 10 to given value

# An iterable user defined type
class Test:

    # Constructor
    def __init__(self, limit):
        self.limit = limit

    # Creates iterator object
    # Called when iteration is initialized
    def __iter__(self):
        self.x = 10
        return self

    # To move to next element. In Python 3,
    # we should replace next with __next__
    def __next__(self):

        # Store current value ofx
        x = self.x

        # Stop iteration if limit is reached
        if x > self.limit:
            raise StopIteration

        # Else increment and return old value
        self.x = x + 1;
        return x

# Prints numbers from 10 to 15
for i in Test(15):
    print(i)

# Prints nothing
for i in Test(5):
    print(i)
```

**输出:**

```py
10
11
12
13
14
15

```

在接下来的迭代中，for 循环在内部(我们看不到)使用迭代器对象遍历 iterable

## 蟒蛇 3

```py
# Sample built-in iterators

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

[**Python 中的生成器**](https://www.geeksforgeeks.org/generators-in-python/)
本文由 **Shwetanshu Rohatgi** 供稿。如果您发现任何不正确的地方，请写评论，或者您想分享更多关于上面讨论的主题的信息