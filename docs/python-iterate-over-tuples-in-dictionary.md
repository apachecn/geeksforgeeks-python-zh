# Python–迭代字典中的元组

> 原文:[https://www . geeksforgeeks . org/python-字典中元组的迭代/](https://www.geeksforgeeks.org/python-iterate-over-tuples-in-dictionary/)

在本文中，我们将讨论如何在 Python 中迭代字典中的元组。

## 方法 1:使用索引

我们可以通过使用索引来获取特定的元组:

**语法:**

```py
dictionary_name[index]
```

迭代特定索引中的整个元组值

```py
for i in range(0, len(dictionary_name[index])):
    print(dictionary_name[index][i]
```

**示例:**

## 计算机编程语言

```py
# Ininitalizing a dictionary
myDict = {1: ("Apple", "Boy", "Cat"),
          2: ("Geeks", "For", "Geeks"),
          3: ("I", "Am", "Learning", "Python")}

print("Tuple mapped with the key 1 =>"),

# Directly printing entire tuple mapped 
# with the key 1
print(myDict[1])

print("Tuple mapped with the key 2 =>"),

# Printing tuple elements mapped with 
# the key 2 one by one
for each in myDict[2]:
    print(each),

print("")
print("Tuple mapped with the key 3 =>"),

# Accessing tuple elements mapped with 
# the key 3 using index
for i in range(0, len(myDict[3])):
    print(myDict[3][i]),
```

**输出:**

```py
Tuple mapped with the key 1 =>
('Apple', 'Boy', 'Cat')
Tuple mapped with the key 2 =>
Geeks
For
Geeks

Tuple mapped with the key 3 =>
I
Am
Learning
Python
```

## 方法 2:使用 values()方法

我们可以使用 [dictionary.values()](https://www.geeksforgeeks.org/python-dictionary-values/) 循环遍历字典中的元组

**语法:**

```py
for i in dictionary_name.values():
  for j in i:
      print(j)
  print(" ")
```

**示例:**

## 蟒蛇 3

```py
# Ininitalizing a dictionary
myDict = {1: ("Apple", "Boy", "Cat"),
          2: ("Geeks", "For", "Geeks"),
          3: ("I", "Am", "Learning", "Python")}

# iterate over all tuples using
# values() method
for i in myDict.values():
    for j in i:
        print(j)
    print(" ")
```

**输出:**

```py
Apple
Boy
Cat

Geeks
For
Geeks

I
Am
Learning
Python
```