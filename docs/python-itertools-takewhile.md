# python–etrtools . take while()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-etrtools-take while/

[itertools](https://www.geeksforgeeks.org/python-itertools/) 是 Python 中的一个模块，它有一组用于处理迭代器的函数。它们使得遍历像列表和字符串这样的数据项变得非常容易。一个这样的 itertools 函数是`takewhile()`。

**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

## takewhile()

这允许从 iterable 中考虑一个项目，直到指定的谓词第一次变为 false。在大多数情况下，iterable 是一个列表或字符串。顾名思义**“取”**的素从序*“而”*的谓语是**“真”**。该函数属于类别**“终止迭代器”**。输出不能直接使用，必须转换为另一种可迭代形式。大多数情况下，它们被转换成列表。

**语法:**

```py
takewhile(predicate, iterable)
```

`predicate`不是内置函数就是用户自定义函数。它甚至可以是 lambda 函数。

下面给出了使用简单 if-else 的这个函数的一般实现。

```py
def takewhile(predicate, iterable):
   for i in iterable:
       if predicate(i):
            return(i)
       else:
            break
```

函数`takewhile()`以谓词和可迭代函数为自变量。迭代该表以检查它的每个元素。如果指定谓词上的元素计算结果为真，则返回。否则，循环终止。

**示例 1:list 和 takewhile()**
考虑一个整数列表。我们只需要输出中的偶数。看看下面的代码，看看如果我们使用`takewhile()`会发生什么。

```py
from itertools import takewhile

# function to check whether 
# number is even
def even_nos(x):
     return(x % 2 == 0)

# iterable (list)
li =[0, 2, 4, 8, 22, 34, 6, 67]

# output list
new_li = list(takewhile(even_nos, li))

print(new_li)
```

**Output:**

```py
[0, 2, 4, 8, 22, 34, 6]

```

**示例 2: Strings and takewhile()**
考虑一个字母数字字符串。现在我们需要取元素，只要它们是数字。

```py
from itertools import takewhile

# function to test the elements
def test_func(x):

    print("Testing:", x)
    return(x.isdigit())

# using takewhile  with for-loop
for i in takewhile(test_func, "11234erdg456"):

    print("Output :", i)
    print()
```

**输出:**

```py
Testing: 1
Output : 1

Testing: 1
Output : 1

Testing: 2
Output : 2

Testing: 3
Output : 3

Testing: 4
Output : 4

Testing: e

```

可迭代的也可以直接传递。在将它们传递给 `takewhile()`函数之前，并不强制将它们分配给某个变量。

**示例 3:take while()**
中的 lambda 函数考虑输入字符串的元素，直到遇到“s”。

```py
from itertools import takewhile

# input string
st ="GeeksforGeeks"

# consider elements until 
# 's' is encountered
li = list(takewhile(lambda x:x !='s', st))

print(li)
```

**输出:**

```py
['G', 'e', 'e', 'k']

```

**示例 4:**
按照随机顺序列出字母，并考虑元素，直到遇到“e”或“I”或“u”。

```py
import random
from itertools import takewhile

# generating alphabets in random order
li = random.sample(range(97, 123), 26)
li = list(map(chr, li))

print("The original list list is :")
print(li)

# consider the element until
# 'e' or 'i' or 'o' is encountered
new_li = list(takewhile(lambda x:x not in ['e', 'i', 'o'],
                        li))

print("\nThe new list is :")
print(new_li)
```

**Output:**

> 原始列表列表为:
> ['v '，' u '，' k '，' j '，' r '，' q '，' n '，' y '，' a '，' x '，' I '，' p '，' e '，' w '，' b '，' t '，' s '，' l '，' z '，' m '，' f '，' c '，' g '，' d '，' o '，' h']
> 
> 新列表为:
> ['v '，' u '，' k '，' j '，' r '，' q '，' n '，' y '，' a '，' x']