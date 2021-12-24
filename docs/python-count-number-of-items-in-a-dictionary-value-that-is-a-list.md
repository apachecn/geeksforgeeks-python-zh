# Python |计算作为列表的字典值中的项数

> 原文:[https://www . geesforgeks . org/python-计数-字典中的项目数-值-即列表/](https://www.geeksforgeeks.org/python-count-number-of-items-in-a-dictionary-value-that-is-a-list/)

在 Python 中，[字典](https://www.geeksforgeeks.org/python-dictionary/)是一个无序的、可变的、有索引的集合。字典是用花括号写的，它们有键和值。它用于散列特定的密钥。

一本字典有多对`key:value` 。可以有多个对，其中对应于一个键的值是一个列表。为了检查该值是否是一个列表，我们使用 Python 中内置的`[isinstance()](https://www.geeksforgeeks.org/python-isinstance-method/)`方法。

`isinstance()`方法取两个参数:

```
object - object to be checked
classinfo - class, type, or tuple of classes and types
```

无论对象是否是给定类的实例，它都返回一个布尔值。

让我们讨论不同的方法来计算字典值(即列表)中的项数。

**方法#1** 使用`in` 运算符

```
# Python program to count number of items
# in a dictionary value that is a list.
def main():

    # defining the dictionary
    d = {'A' : [1, 2, 3, 4, 5, 6, 7, 8, 9],
        'B' : 34,
        'C' : 12,
        'D' : [7, 8, 9, 6, 4] }

    # using the in operator
    count = 0
    for x in d:
        if isinstance(d[x], list):
            count += len(d[x])
    print(count)

# Calling Main    
if __name__ == '__main__':
    main()
```

**Output:**

```
14

```

**方法 2:** 使用列表理解

```
# Python program to count number of items
# in a dictionary value that is a list.
def main():

    # defining the dictionary
    d = {'A' : [1, 2, 3, 4, 5, 6, 7, 8, 9],
        'B' : 34,
        'C' : 12,
        'D' : [7, 8, 9, 6, 4] }

    # using list comprehension
    print(sum([len(d[x]) for x in d if isinstance(d[x], list)]))

if __name__ == '__main__':
    main()
```

**Output:**

```
14

```

**方法 3:** 使用 `dict.items()`

```
# Python program to count number of items
# in a dictionary value that is a list.
def main():

    # defining the dictionary
    d = { 'A' : [1, 2, 3, 4, 5, 6, 7, 8, 9],
        'B' : 34,
        'C' : 12,
        'D' : [7, 8, 9, 6, 4] }

    # using dict.items()
    count = 0
    for key, value in d.items():
        if isinstance(value, list):
              count += len(value)
    print(count)

if __name__ == '__main__':
    main()
```

**Output:**

```
14

```

**方法#4:** 使用`enumerate()`

```
# Python program to count number of items
# in a dictionary value that is a list.
def main():

    # defining the dictionary
    d = {'A' : [1, 2, 3, 4, 5, 6, 7, 8, 9],
        'B' : 34,
        'C' : 12,
        'D' : [7, 8, 9, 6, 4] }

    # using enumerate()
    count = 0
    for x in enumerate(d.items()):

        # enumerate function returns a tuple in the form
        # (index, (key, value)) it is a nested tuple
        # for accessing the value we do indexing x[1][1]
        if isinstance(x[1][1], list):
            count += len(x[1][1])
    print(count)

if __name__ == '__main__':
    main()
```

**Output:**

```
14

```