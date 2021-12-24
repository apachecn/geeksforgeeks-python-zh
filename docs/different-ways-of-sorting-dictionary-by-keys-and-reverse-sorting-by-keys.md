# 字典按键排序和反向按键排序的不同方式

> 原文:[https://www . geesforgeks . org/不同的排序方式-按键字典和按键反向排序/](https://www.geeksforgeeks.org/different-ways-of-sorting-dictionary-by-keys-and-reverse-sorting-by-keys/)

**先决条件:**[Python 词典](https://www.geeksforgeeks.org/python-dictionary/)

字典是一个无序的、可变的和有索引的集合。在 Python 中，字典是用花括号写的，它们有键和值。我们可以使用键访问字典的值。在本文中，我们将讨论 10 种不同的按键排序 Python 字典的方法，以及按键反向排序的方法。

### **使用排序的()和键():**

**keys()** 方法返回一个视图对象，该对象显示字典中所有键的列表。 **sorted()** 用于对字典的关键字进行排序。

**示例:**

```py
Input:
my_dict = {'c':3, 'a':1, 'd':4, 'b':2}

Output:
a: 1
b: 2
c: 3
d: 4

```

## 蟒 3

```py
# Initialising a dictionary
my_dict = {'c':3, 'a':1, 'd':4, 'b':2}

# Sorting dictionary
sorted_dict = my_dict.keys()
sorted_dict = sorted(sorted_dict)

# Printing sorted dictionary
print("Sorted dictionary using sorted() and keys() is : ")
for key in sorted_dict:
    print(key,':', my_dict[key])
```

**输出**

```py
Sorted dictionary using sorted() and keys() is : 
a : 1
b : 2
c : 3
d : 4

```

### **使用排序的()和项目():**

**items()** 方法用于返回所有字典键都有值的列表。它返回一个视图对象，该对象显示给定字典的(键、值)元组对的列表。 **sorted()** 用于对字典的关键字进行排序。

**示例:**

```py
Input:
my_dict = {2:'three', 1:'two', 4:'five', 3:'four'}

Output:
1  'two'
2  'three'
3  'Four'
4  'Five'

```

## 蟒 3

```py
# Initialising dictionary
my_dict = {2: 'three', 1: 'two', 4: 'five', 3: 'four'}

# Sorting dictionary
sorted_dict = sorted(my_dict.items())

# Printing sorted dictionary
print("Sorted dictionary using sorted() and items() is :")
for k, v in sorted_dict:
    print(k, v)
```

**输出**

```py
Sorted dictionary using sorted() and items() is :
1 two
2 three
3 four
4 five

```

### **单行使用排序的()和键:**

这里，我们在一行中同时使用了 sorted()和 key()。

**例:**

```py
Input:
my_dict = {'c':3, 'a':1, 'd':4, 'b':2}

Output:
Sorted dictionary is :  ['a','b','c','d']

```

## 蟒 3

```py
# Initialising a dictionary
my_dict = {'c': 3, 'a': 1, 'd': 4, 'b': 2}
# Sorting dictionary
sorted_dict = sorted(my_dict.keys())

# Printing sorted dictionary
print("Sorted dictionary is : ", sorted_dict)
```

**输出**

```py
Sorted dictionary is :  ['a', 'b', 'c', 'd']

```