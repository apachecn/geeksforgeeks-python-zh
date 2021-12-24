# python–te tools . count()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-etrtools-count/

[Python Itertools](https://www.geeksforgeeks.org/python-itertools/) 是创建复杂迭代器的好方法，有助于获得更快的执行时间和编写内存高效的代码。`Itertools`为我们提供了创建无限序列的函数，`itertools.count()`就是这样一个函数，它做的正是它听起来的样子，它算数！

**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

## itertools . count()

`itertools.count()`通常与`map()`一起使用，以生成连续的数据点，这在处理数据时非常有用。它也可以与`zip`一起使用，通过将计数作为参数来添加序列。

> **语法:** itertools.count(start=0，step=1)
> 
> **参数:**
> **开始:**序列的开始(默认为 0)
> **步骤:**连续数字之间的差值(默认为 1)
> 
> **返回:**返回一个计数对象，其。__next__()方法返回连续的值。

让我们使用一些简单的 Python 程序来深入了解这把强大的剑。

**示例#1:创建均匀间隔的数字列表**
`itertools.count()`可用于轻松生成无限递归序列。让我们看看

```py
# Program for creating a list of
# even and odd list of integers
# using count()

from itertools import count

# creates a count iterator object
iterator =(count(start = 0, step = 2))

# prints a odd list of integers
print("Even list:", 
      list(next(iterator) for _ in range(5)))

# creates a count iterator object
iterator = (count(start = 1, step = 2))

# prints a odd list of integers
print("Odd list:", 
      list(next(iterator) for _ in range(5)))
```

**输出:**

```py
Even list: [0, 2, 4, 6, 8]
Odd list: [1, 3, 5, 7, 9]

```

同样，我们也可以生成一系列负数和浮点数。为提高浮点数的准确性，请使用`(start + step * i for i in count())`。

**例 2:使用`itertools.count()`**
仿真`enumerate()`如前所述，`count()`可以和`zip()`一起使用。让我们看看如何在事先不知道列表长度的情况下，用它来模仿`enumerate()`的功能！

```py
# Program to emulate enumerate() 
# using count()

# list containing some strings
my_list =["Geeks", "for", "Geeks"]

# count spits out integers for 
# each value in my list
for i in zip(count(start = 1, 
                   step = 1), my_list):

    # prints tuple in an enumerated 
    # format
    print(i)
```

**输出:**

```py
(1, 'Geeks')
(2, 'for')
(3, 'Geeks')

```

**注意:**使用`itertools.count()`时一定要格外小心，因为很容易陷入无限循环。

以下代码的功能与`while True:`相同，因此必须指定适当的终止条件。

```py
for i in count(start=0, step=2): 
    print(i)

```