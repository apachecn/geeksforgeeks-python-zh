# python 中的 _ _ getslice _

> 原文:[https://www.geeksforgeeks.org/__getslice__-in-python/](https://www.geeksforgeeks.org/__getslice__-in-python/)

在 python 中，邓德方法是那些在方法名中有两个前缀和后缀下划线的方法。它们也被称为 **[魔法](https://www.geeksforgeeks.org/dunder-magic-methods-python/)** 。 **Dunder** 表示“**双下划线**”。它们通常用于运算符重载。这些方法不是由用户直接调用的，而是从类内部调用的。邓德方法的一些例子是`__init__, __repr__, __getslice__, __getitem__`。

## __getslice__()

**__getslice__(self，I，j)** 在对象上调用切片操作符即`self[i:j]`时被调用。返回的对象应该与 self 属于同一类型。它既可以用于可变序列，也可以用于不可变序列。

**注意:** `__getslice__`由于 Python 2.0 而被弃用，在 Python 3.x 中不可用。我们在 python 3.x 中使用 [__getitem__](https://www.geeksforgeeks.org/implementing-slicing-in-__getitem__/) 方法来代替它

**例 1:**

```py
# program to demonstrate __getslice__ method

class MyClass:
    def __init__(self, string):
        self.string = string

    # method for creating list of words
    def getwords(self):
        return self.string.split()

    # method to perform slicing on the
    # list of words
    def __getslice__(self, i, j):
        return self.getwords()[max(0, i):max(0, j)]

# Driver Code 
if __name__ == '__main__': 

    # object creation
    obj = MyClass("Hello World ABC")

    # __getslice__ method called internally
    # from the class
    sliced = obj[0:2]

    # print the returned output
    # return type is list
    print(sliced)
```

**输出**

```py
['Hello', 'World']
```

**例 2:**

```py
# program to demonstrate __getslice__ method

class MyClass:
    def __init__(self, string):
        self.string = string

    # method for creating list of words
    def getwords(self):
        return self.string.split()

    # method to perform slicing on
    # the list of words
    def __getslice__(self, i, j):
        return self.getwords()[max(0, i):max(0, j)]

# Driver Code 
if __name__ == '__main__': 

    # object creation
    obj = MyClass("Hello World ABC")

    # __getslice__ method called internally
    # from the class
    sliced = obj[0:0]

    # print the returned output
    # return type is list
    print(sliced)
```

**输出**

```py
[]
```