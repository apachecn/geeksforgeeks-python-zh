# Python 中追加、扩展和插入的区别

> 原文:[https://www . geesforgeks . org/python 中追加、扩展和插入的区别/](https://www.geeksforgeeks.org/difference-between-append-extend-and-insert-in-python/)

**列表**就像动态大小的数组，用其他语言声明(C++中的 vector 和 Java 中的 ArrayList)。列表不必总是相同的，这使得它成为 [Python](https://www.geeksforgeeks.org/python-programming-language/) 中最强大的工具。单个列表可能包含整数、字符串和对象等数据类型。

列表是可变的，因此，即使在创建之后，它们也可以被更改。列表有各种方法，最常用的列表方法有 *append()、insert()、extend()* 等。在本文中，我们将讨论 Python 列表中的 *append()、insert()和 extend()* 方法之间的区别。

### **追加**

它在列表的末尾添加一个元素。在 append 函数中传递的参数作为单个元素添加到列表的末尾，列表的长度增加 1。

**语法:**

```py
list_name.append(element)
```

元素可以是字符串、整数、元组或其他列表。

**示例:**

## 蟒蛇 3

```py
# python program to demonstrate
# working of append function

# assign list
l = ['geeks']

# use method
l.append('for')
l.append('geeks')

# display list
print(l)
```

**输出:**

```py
['geeks', 'for', 'geeks']
```

### **插入**

此方法可用于在任何所需位置插入值。它需要两个参数-元素和元素必须插入的索引。

**语法:**

```py
list_name(index,element)
```

元素可以是字符串、对象或整数。

**示例:**

## 蟒蛇 3

```py
# python program to demonstrate
# working of insert function

# assign list
l = ['geeks', 'geeks']

# use method
l.insert(1, 'for')

# display list
print(l)
```

**输出:**

```py
['geeks', 'for', 'geeks']
```

### **延伸**

这个方法会将 iterable 的每个元素(元组、字符串或列表)追加到列表的末尾，并通过作为参数传递的 iterable 的元素数量来增加列表的长度。

**语法:**

```py
list_name.extend(iterable)
```

**示例:**

## 蟒蛇 3

```py
# python program to demonstrate
# working of extend function

# assign list
l = ['hello', 'welcome', 'to']

# use method
l.extend(['geeks', 'for', 'geeks'])

# display list
print(l)
```

**输出:**

```py
['hello', 'welcome', 'to', 'geeks', 'for', 'geeks']
```

### 追加、扩展和插入之间的区别

<figure class="table">

| **追加()** | **插入()** | **extend()** |
| --- | --- | --- |
| 作为参数传递的元素被附加到列表的末尾 | 通过将索引作为参数一起传递，可以将作为参数传递的元素插入到任何需要的位置。 | 作为参数传递的 iterable 的每个元素都被追加到列表的末尾。 |
| 作为参数传递的 iterable 在不做任何更改的情况下作为单个元素追加到列表的末尾。 | 作为参数传递的 iterable 在不做任何更改的情况下作为单个元素追加到列表的所需索引中。 | 作为参数传递的 iterable 会将其每个元素附加到列表的末尾 |
| 列表长度增加 1 | 列表长度增加 1 | 列表的长度随着表中元素的数量而增加。 |
| 时间复杂度为 O(1) | 具有 0(n)的线性复杂度。 | 时间复杂度为 O(k)，其中 k 是可迭代的长度。 |

</figure>

**比较单个程序中的方法:**

## 蟒蛇 3

```py
# Python program to demonstrate
# comparison between the three methods

# assign lists
list_1 = [1, 2, 3]
list_2 = [1, 2, 3]
list_3 = [1, 2, 3]

a = [2, 3]

# use methods
list_1.append(a)
list_2.insert(3, a)
list_3.extend(a)

# display lists
print(list_1)
print(list_2)
print(list_3)
```

**输出:**

```py
[1, 2, 3, [2, 3]]
[1, 2, 3, [2, 3]]
[1, 2, 3, 2, 3]
```