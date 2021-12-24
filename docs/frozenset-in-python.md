# Python 中的 frozenset()

> 原文:[https://www.geeksforgeeks.org/frozenset-in-python/](https://www.geeksforgeeks.org/frozenset-in-python/)

**frozenset()** 是 Python 中的一个内置函数，它将一个可迭代的对象作为输入，并使它们不可变。简单地说，它冻结了可重复的对象，使它们不可改变。

在 Python 中，frozenset 与 set 相同，只是 frozenset 是不可变的，这意味着 frozen set 中的元素一旦创建就不能添加或删除。该函数将输入作为任何可迭代对象，并将它们转换为不可变对象。元素的顺序不能保证被保留。

> **语法:**frozenset(iterable _ object _ name)
> **参数:**该函数接受 iterable 对象作为输入参数。
> **返回类型:**该函数返回一个等价的 frozenset 对象。

下面的例子解释得很清楚。

**示例#1:**
如果没有参数被传递给 frozenset()函数，那么它返回一个空的 frozenset 类型对象。

## 蟒蛇 3

```py
# Python program to understand frozenset() function

# tuple of numbers
nu = (1, 2, 3, 4, 5, 6, 7, 8, 9)

# converting tuple to frozenset
fnum = frozenset(nu)

# printing details
print("frozenset Object is : ", fnum)
```

**Output:** 

```py
frozenset Object is :  frozenset({1, 2, 3, 4, 5, 6, 7, 8, 9})
```

**例 2:frozenset()**的用法。
由于 frozenset 对象是不可变的，所以它们主要用作字典中的键或其他集合的元素。下面的例子解释得很清楚。

## 蟒蛇 3

```py
# Python program to understand use
# of frozenset function

# creating a dictionary
Student = {"name": "Ankit", "age": 21, "sex": "Male",
           "college": "MNNIT Allahabad", "address": "Allahabad"}

# making keys of dictionary as frozenset
key = frozenset(Student)

# printing keys details
print('The frozen set is:', key)
```

**Output:** 

```py
The frozen set is: frozenset({'sex', 'age', 'address', 'name', 'college'})
```

**例 3:** 警告
如果我们误想更改 *frozenset* 对象，那么它会抛出一个错误“*‘frozenset’对象不支持物品分配*”。

## 蟒蛇 3

```py
# Python program to understand
# use of frozenset function

# creating a list
favourite_subject = ["OS", "DBMS", "Algo"]

# making it frozenset type
f_subject = frozenset(favourite_subject)

# below line will generate error

f_subject[1] = "Networking"
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/0fbd773df8aa631590ed0f3f865c1437.py", line 12, in 
    f_subject[1] = "Networking"
TypeError: 'frozenset' object does not support item assignment
```