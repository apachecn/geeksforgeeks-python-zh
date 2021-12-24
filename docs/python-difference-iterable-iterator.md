# Python |可迭代和迭代器的区别

> 原文:[https://www . geesforgeks . org/python-difference-iterator-iterator/](https://www.geeksforgeeks.org/python-difference-iterable-iterator/)

**可迭代**是一个可以迭代的对象。当传递给`iter()`方法时，它会生成一个迭代器。**迭代器**是一个对象，用于使用 __next__()方法对可迭代对象进行迭代。迭代器有 `__next__()` 方法，返回对象的下一项。

请注意，每个迭代器也是可迭代的，但不是每个可迭代的都是迭代器。例如，列表是可迭代的，但列表不是迭代器。迭代器可以通过使用函数`iter()`从可迭代创建。为了实现这一点，对象的类需要一个返回迭代器的方法`__iter__`，或者一个以 0 开始的顺序索引的`__getitem__`方法。

**代码#1** :

```
for city in ["Berlin", "Vienna", "Zurich"]:
    print(city)

print("\n")

for city in ("Python", "Perl", "Ruby"):
    print(city)

print("\n")

for char in "Iteration is easy":
    print(char, end = " ")
```

输出:

```
Berlin
Vienna
Zurich

Python
Perl
Ruby

I t e r a t i o n   i s   e a s y 
```

当执行 for 循环时，for 语句调用对象上的 `iter()` ，它应该循环该对象。如果这个调用成功，iter 调用将返回一个定义方法`__next__()`的迭代器对象，该对象一次访问一个对象的元素。如果没有其他可用元素，则 `__next__()`方法将引发`**StopIteration**` 异常。for 循环将在捕获到 StopIteration 异常后立即终止。

我们使用下一个()内置函数调用 `__next__()`方法。

**代码#2 :** 如果对象“obj”是可迭代的，函数“iterable”将返回真，否则返回假。

```
# list of cities
cities = ["Berlin", "Vienna", "Zurich"]

# initialize the object
iterator_obj = iter(cities)

print(next(iterator_obj))
print(next(iterator_obj))
print(next(iterator_obj))
```

输出:

```
Berlin
Vienna
Zurich

```

**注意:**如果‘next(iterator _ obj)’被再次调用，它将返回‘stop iteration’。

**代码#3 :** 检查对象是否可重复

```
# Function to check object
# is iterable or not 
def iterable(obj):
    try:
        iter(obj)
        return True

    except TypeError:
        return False

# Driver Code     
for element in [34, [4, 5], (4, 5),
             {"a":4}, "dfsdf", 4.5]:

    print(element, " is iterable : ", iterable(element))
```

输出:

```
34  is iterable :  False
[4, 5]  is iterable :  True
(4, 5)  is iterable :  True
{'a': 4}  is iterable :  True
dfsdf  is iterable :  True
4.5  is iterable :  False

```