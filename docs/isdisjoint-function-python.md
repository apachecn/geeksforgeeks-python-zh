# Python 中的 isdisjoint()函数

> 原文:[https://www.geeksforgeeks.org/isdisjoint-function-python/](https://www.geeksforgeeks.org/isdisjoint-function-python/)

**Python 集合 is isjoint()函数**检查两个集合是否不相交，如果不相交则返回 True，否则返回 False。当两个集合的交集为空时，称它们是不相交的。简单地说，它们之间没有任何共同的元素。

**示例:**

```
Let set A = {2, 4, 5, 6}
and set B = {7, 8, 9, 10} 
```

集合 A 和集合 B 被称为不相交的集合，因为它们的交集为空。他们之间没有任何共同的因素。

### Python isdisjoint() **语法**

> set1.isdisjoint(set2)

### Python isdisjoint() **参数**

**是一个关节()Python 方法**只接受一个**参数。**它还可以将一个可迭代的(列表、元组、字典和字符串)变为不相交的()。isdisjoint()方法会自动将 iterables 转换为 set，并检查这些 set 是否不相交。

### Python isdisjoint() **返回值**

> 如果两个集合不相交，则返回**真**。如果两个集合不是不相交的，则
> 返回 **False** 。

## Python 集 isdisjoint()示例

### 示例 1:工作集是 isjoin()

## 蟒蛇 3

```
# Python3 program for isdisjoint() function
set1 = {2, 4, 5, 6}
set2 = {7, 8, 9, 10}
set3 = {1, 2}

# checking of disjoint of two sets
print("set1 and set2 are disjoint?",
      set1.isdisjoint(set2))

print("set1 and set3 are disjoint?",
      set1.isdisjoint(set3))
```

**输出:**

```
set1 and set2 are disjoint? True
set1 and set3 are disjoint? False
```

### 示例 2:以其他 Iterables 作为参数的 Python isdisjoint()

## 蟒蛇 3

```
# Set
A = {2, 4, 5, 6}

# List
lis = [1, 2, 3, 4, 5]

# Dictionary dict, Set is formed on Keys
dict = {1: 'Apple', 2: 'Orage'}

# Dictionary dict2
dict2 = {'Apple': 1, 'Orage': 2}

print("Set A and List lis disjoint?", A.isdisjoint(lis))
print("Set A and dict are disjoint?", A.isdisjoint(dict))
print("Set A and dict2 are disjoint?", A.isdisjoint(dict2))
```

**输出:**

```
Set A and List lis disjoint? False
Set A and dict are disjoint? False
Set A and dict2 are disjoint? True
```