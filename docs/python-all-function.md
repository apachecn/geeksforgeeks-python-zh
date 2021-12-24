# Python–all()函数

> 原文:[https://www.geeksforgeeks.org/python-all-function/](https://www.geeksforgeeks.org/python-all-function/)

all()函数是 Python 中的一个内置函数，如果给定表(列表、字典、元组、集合等)的所有元素都为真，则返回 true，否则返回 False。如果可迭代对象为空，它也返回真。

> **语法:** all(可迭代)
> 
> **参数:**iteratable:是字典、元组、列表、集合等可迭代对象。

**示例#1:使用列表对所有()进行操作:**

**代码:**

## 蟒蛇 3

```
# All elements of list are true
l = [4, 5, 1]
print(all(l))

# All elements of list are false
l = [0, 0, False]
print(all(l))

# Some elements of list are
# true while others are false
l = [1, 0, 6, 7, False]
print(all(l))

# Empty List
l = []
print(all(l))
```

**输出:**

```
True
False
False
True
```

**示例#2:使用元组处理所有()。**

## 蟒蛇 3

```
# All elements of tuple are true
t = (2, 4, 6)
print(all(t))

# All elements of tuple are false
t = (0, False, False)
print(all(t))

# Some elements of tuple
# are true while others are false
t = (5, 0, 3, 1, False)
print(all(t))

# Empty tuple
t = ()
print(all(t))
```

**输出:**

```
True
False
False
True
```

**示例#3:使用集合处理所有()。**

## 蟒蛇 3

```
# All elements of set are true
s = {1, 1, 3}
print(all(s))

# All elements of set are false
s = {0, 0, False}
print(all(s))

# Some elements of set
# are true while others are false
s = {1, 2, 0, 8, False}
print(all(s))

# Empty set
s = {}
print(all(s))
```

**输出:**

```
True
False
False
True
```

**示例#4:使用字典处理所有()。**

注意:在字典的情况下，如果字典的所有键都为真或者字典为空，all()返回 true，否则返回 false。

## 蟒蛇 3

```
# All elements of dictionary are true
d = {1: "Hello", 2: "Hi"}
print(all(d))

# All elements of dictionary are false
d = {0: "Hello", False: "Hi"}
print(all(d))

# Some elements of dictionary
# are true while others are false
d = {0: "Salut", 1: "Hello", 2: "Hi"}
print(all(d))

# Empty dictionary
d = {}
print(all(d))
```

**输出:**

```
True
False
False
True
```

**示例#5:使用字符串处理所有()。**

## 蟒蛇 3

```
# Non-Empty String
s = "Hi There!"
print(all(s))

# Non-Empty String
s = "000"
print(all(s))

# Empty string
s = ""
print(all(s))
```

**输出:**

```
True
True
True
```