# Python |计数器对象|元素()

> 原文:[https://www . geesforgeks . org/python-counter-objects-elements/](https://www.geeksforgeeks.org/python-counter-objects-elements/)

[**计数器类**](https://www.geeksforgeeks.org/counters-in-python-set-1/)**是 Python3 中**集合**模块提供的一种特殊类型的对象数据集。集合模块为用户提供了专门的容器数据类型，从而为 Python 的通用内置功能(如字典、列表和元组)提供了一种替代方案。**

****计数器**是一个子类，用于计数可散列的对象。它在被调用时隐式地创建一个 iterable 的哈希表。**

****elements()** 是 Counter 类的函数之一，在 Counter 对象上调用时会返回 Counter 对象中所有已知元素的 itertool。**

> ****参数:**不带任何参数
> **返回类型:**返回 Counter 对象中所有计数为正的元素的 itertool
> **错误和异常:**
> **- >** 直接打印时会打印垃圾值，因为它返回的是 ITER tool，而不是特定的数据容器。
> **- >** 如果一个项目的计数已经在 Counter 对象中初始化，那么它将忽略零值和负值的项目。**

****代码#1:** 在简单的数据容器上处理元素()**

## **蟒蛇 3**

```py
# import counter class from collections module
from collections import Counter

# Creation of a Counter Class object using
# string as an iterable data container
x = Counter("geeksforgeeks")

# printing the elements of counter object
for i in x.elements():
    print ( i, end = " ")
```

****输出:****

```py
g g e e e e k k s s f o r 
```

****代码#2:** 具有不同数据容器的各种计数器对象上的元素**

## **蟒蛇 3**

```py
# import counter class from collections module
from collections import Counter

# Creation of a Counter Class object using
# a string as an iterable data container
# Example - 1
a = Counter("geeksforgeeks")

# Elements of counter object
for i in a.elements():
    print ( i, end = " ")
print()

# Example - 2
b = Counter({'geeks' : 4, 'for' : 1,
            'gfg' : 2, 'python' : 3})

for i in b.elements():
    print ( i, end = " ")
print()

# Example - 3
c = Counter([1, 2, 21, 12, 2, 44, 5,
              13, 15, 5, 19, 21, 5])

for i in c.elements():
    print ( i, end = " ")
print()             

# Example - 4
d = Counter( a = 2, b = 3, c = 6, d = 1, e = 5)

for i in d.elements():
    print ( i, end = " ")
```

****输出:****

```py
g g e e e e k k s s f o r 
geeks geeks geeks geeks for gfg gfg python python python 
1 2 2 21 21 12 44 5 5 5 13 15 19 
a a b b b c c c c c c d e e e e e 
```

****代码#3:** 演示直接打印时()返回哪些元素**

## **蟒蛇 3**

```py
# import Counter from collections
from collections import Counter

# creating a raw data-set
x = Counter ("geeksforgeeks")

# will return a itertools chain object
# which is basically a pseudo iterable container whose
# elements can be used when called with a iterable tool
print(x.elements())
```

****输出:****

```py
itertools.chain object at 0x037209F0
```

****代码#4:** 当计数器中的项目计数初始化为负值或零时。**

## **蟒蛇 3**

```py
# import Counter from collections
from collections import Counter

# creating a raw data-set using keyword arguments
x = Counter (a = 2, x = 3, b = 3, z = 1, y = 5, c = 0, d = -3)

# printing out the elements
for i in x.elements():
    print( "% s : % s" % (i, x[i]), end ="\n")
```

****输出:****

```py
a : 2
a : 2
x : 3
x : 3
x : 3
b : 3
b : 3
b : 3
z : 1
y : 5
y : 5
y : 5
y : 5
y : 5
```

****注意:**我们可以从输出中推断出值小于 1 的项被元素()省略。**

****应用程序:**
计数器对象及其功能共同用于处理海量数据。我们可以看到 Counter()为使用它调用的数据容器创建了一个哈希映射，这比手工处理元素非常有用。它是一个非常高的处理和功能工具之一，甚至可以处理大范围的数据。**