# 如何在 Python 3 中使用 List 作为字典的键？

> 原文:[https://www . geesforgeks . org/如何使用 python 字典中的列表作为关键字-3/](https://www.geeksforgeeks.org/how-to-use-a-list-as-a-key-of-a-dictionary-in-python-3/)

在 Python 中，我们使用[字典](https://www.geeksforgeeks.org/python-dictionary/)来检查项目是否存在。字典使用**键:值**对来搜索键是否存在，以及键是否存在，其值是多少。我们可以使用整数、字符串、元组作为字典键，但不能使用列表作为它的键。原因解释如下。

## Python 字典如何搜索它们的键

如果 Python 字典只是遍历它们的键来检查给定的键是否存在，将需要 **O(N)** 时间。但是 python 字典用 **O(1)** 来检查键是否存在。那么，字典是如何搜索关键字的呢，对于每个关键字，它都会为关键字生成一个[哈希值](https://www.geeksforgeeks.org/hashing-set-1-introduction/)，通过这个哈希值，它可以跟踪它的元素。

## 如果列表被用作字典的关键字
会出现问题

列表是[可变对象](https://www.geeksforgeeks.org/mutable-vs-immutable-objects-in-python/)，这意味着我们可以更改列表中的值，添加或删除列表中的值。因此，如果从列表中生成一个散列函数，然后列表中的项目发生了变化，字典将为该列表生成一个新的散列值，但却找不到它。

例如，如果列表是`a = [1, 2, 3, 4, 5]`，并且假设列表的散列是列表内值的总和。所以 hash(a) = 15。现在我们将 6 附加到 a 上，所以`a = [1, 2, 3, 4, 5, 6]`散列(a) = 21。所以哈希值变了。因此在字典里找不到。

另一个问题是哈希值相同的不同列表。如果`b = [5, 5, 5]`散列(b) = 15。所以如果 a(来自上面相同哈希值的例子)存在于字典中，如果我们搜索 b，那么字典可能会给我们错误的结果。

### 如何处理

我们可以将列表变成不可变的对象，如字符串或元组，然后将其用作关键字。下面是该方法的实现。

```
# Declaring a dictionary
d = {} 

# This is the list which we are 
# trying to use as a key to
# the dictionary
a =[1, 2, 3, 4, 5]

# converting the list a to a string
p = str(a)
d[p]= 1

# converting the list a to a tuple
q = tuple(a) 
d[q]= 1

for key, value in d.items():
    print(key, ':', value)
```

**输出:**

```
[1, 2, 3, 4, 5] : 1
(1, 2, 3, 4, 5) : 1
```