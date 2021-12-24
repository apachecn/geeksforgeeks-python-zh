# 收藏。Python 中的用户列表

> 原文:[https://www . geesforgeks . org/collections-user list-in-python/](https://www.geeksforgeeks.org/collections-userlist-in-python/)

Python **列表**是类似数组的数据结构，但不像它可以是同构的。单个列表可能包含整数、字符串和对象等数据类型。Python 中的列表是有序的，并且有明确的计数。列表中的元素按照一定的顺序进行索引，列表的索引以 0 作为第一个索引。
**注:**更多信息请参考 [Python 列表](https://www.geeksforgeeks.org/python-list/)

## 收藏品。用户列表

Python 支持一个[列表](https://www.geeksforgeeks.org/python-list/)，就像一个名为**用户列表**的容器，存在于**集合**模块中。这个类充当列表对象的包装类。当一个人想要创建一个他们自己的带有一些修改的功能或带有一些新功能的列表时，这个类是有用的。它可以被认为是为列表添加新行为的一种方式。这个类将一个列表实例作为参数，并模拟一个保存在常规列表中的列表。该列表可由该类的数据属性访问。
**语法:**

```
collections.UserList([list])
```

**例 1:**

## 蟒蛇 3

```
# Python program to demonstrate
# userlist

from collections import UserList

L = [1, 2, 3, 4]

# Creating a userlist
userL = UserList(L)
print(userL.data)

# Creating empty userlist
userL = UserList()
print(userL.data)
```

**输出:**

```
[1, 2, 3, 4]
[]
```

**例 2:**

## 蟒蛇 3

```
# Python program to demonstrate
# userlist

from collections import UserList

# Creating a List where
# deletion is not allowed
class MyList(UserList):

    # Function to stop deletion
    # from List
    def remove(self, s = None):
        raise RuntimeError("Deletion not allowed")

    # Function to stop pop from
    # List
    def pop(self, s = None):
        raise RuntimeError("Deletion not allowed")

# Driver's code
L = MyList([1, 2, 3, 4])

print("Original List")

# Inserting to List"
L.append(5)
print("After Insertion")
print(L)

# Deleting From List
L.remove()
```

**输出:**

```
Original List
After Insertion
[1, 2, 3, 4, 5]
```

```
Traceback (most recent call last):
  File "/home/9399c9e865a7493dce58e88571472d23.py", line 33, in 
    L.remove()
  File "/home/9399c9e865a7493dce58e88571472d23.py", line 15, in remove
    raise RuntimeError("Deletion not allowed")
RuntimeError: Deletion not allowed
```