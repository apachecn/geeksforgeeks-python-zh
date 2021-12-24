# Python 任意()函数

> 原文:[https://www.geeksforgeeks.org/python-any-function/](https://www.geeksforgeeks.org/python-any-function/)

**Python any()函数**如果给定可迭代表(列表、字典、元组、集合等)的任何元素为真，则返回真，否则返回假。

> **语法:**任意(可迭代)
> 
> **参数:** Iterable:是字典、元组、列表、集合等可迭代对象。
> 
> **返回:** Python any()函数如果任一项为真，则返回 true。

### **示例#1: Python any()函数列表**

## 蟒蛇 3

```py
# All elements of list are true
l = [ 4, 5, 1]
print(any( l ))

# All elements of list are false
l = [ 0, 0, False]
print(any( l ))

# Some elements of list are
# true while others are false
l = [ 1, 0, 6, 7, False]
print(any( l ))

# Empty List
l = []
print(any( l ))
```

**输出:**

```py
True
False
True
False
```

### **示例#2:使用元组处理任何()函数**

## 蟒蛇 3

```py
# All elements of tuple are true
t = (2, 4, 6)
print(any(t))

# All elements of tuple are false
t = (0, False, False)
print(any(t))

# Some elements of tuple are true while
# others are false
t = (5, 0, 3, 1, False)
print(any(t))

# Empty tuple
t = ()
print(any(t))
```

**输出:**

```py
True
False
True
False
```

### **示例#3:使用集合**工作任何()函数

## 蟒蛇 3

```py
# All elements of set are true
s = { 1, 1, 3}
print(any( s ))

# All elements of set are false
s = { 0, 0, False}
print(any( s ))

# Some elements of set are true while others are false
s = { 1, 2, 0, 8, False}
print(any( s ))

#Empty set
s = {}
print(any( s ))
```

**输出:**

```py
True
False
True
False
```

### **示例#4:使用字典处理任何()函数**

**注意:**在字典的情况下，如果字典的所有键都是假的或者字典是空的，则 any()返回 false。如果至少有一个键为真，任何()都会返回真。

## 蟒蛇 3

```py
# All elements of dictionary are true
d = {1: "Hello", 2: "Hi"}
print(any(d))

# All elements of dictionary are false
d = {0: "Hello", False: "Hi"}
print(any(d))

# Some elements of dictionary
# are true while others are false
d = {0: "Salut", 1: "Hello", 2: "Hi"}
print(any(d))

# Empty dictionary
d = {}
print(any(d))
```

**输出:**

```py
True
False
True
False
```

### **示例#5:** 使用字符串处理任何()函数

## 蟒蛇 3

```py
# Non-Empty String
s = "Hi There!"
print(any(s))

# Non-Empty String
s = "000"
print(any(s))

# Empty string
s = ""
print(any(s))
```

**输出:**

```py
True
True
False
```

### 示例 6: Python 任何带有条件的函数

它检查任何满足条件的元素，如果找到任何一个元素，则返回真。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Check if any element in list satisfies a condition
# Using any()

# initializing list
test_list = [4, 5, 8, 9, 10, 17]

# printing list
print("The original list : " + str(test_list))

# Check if any element in list satisfies a condition
# Using any()
res = any(ele > 10 for ele in test_list)

# Printing result
print("Does any element satisfy specified condition ? : " + str(res))
```

**输出:**

```py
The original list : [4, 5, 8, 9, 10, 17]
Does any element satisfy specified condition ? : True
```

### **示例#7: P** 任何带 for 循环的()函数

## 蟒蛇 3

```py
def any(list_x):
    for item in list_x:
        if item:
            return True
    return False

x = [4, 5, 8, 9, 10, 17]
print(any(x))
```

**输出:**

```py
True
```