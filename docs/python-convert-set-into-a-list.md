# Python |将集合转换成列表

> 原文:[https://www . geesforgeks . org/python-convert-set-to-a-list/](https://www.geeksforgeeks.org/python-convert-set-into-a-list/)

给定一个集合，编写一个 Python 程序，将给定的集合转换成列表。

**示例:**

```
Input : {1, 2, 3, 4}
Output : [1, 2, 3, 4]

Input : {'Geeks', 'for', 'geeks'}
Output : ['Geeks', 'for', 'geeks']

```

**使用`list(set_name)`接近#1 :** 。

简单的使用`list(set_name)`就可以进行列表的类型转换。

```
# Python3 program to convert a 
# set into a list
my_set = {'Geeks', 'for', 'geeks'}

s = list(my_set)
print(s)
```

**Output:**

```
['Geeks', 'for', 'geeks']

```

```
# Python3 program to convert a 
# set into a list
def convert(set):
    return list(set)

# Driver function
s = set({1, 2, 3})
print(convert(s))
```

**Output:**

```
[1, 2, 3]

```

**使用`sorted()`方法接近#2 :**

使用`sorted()`功能将集合按照定义的顺序转换成列表。这种方法的唯一缺点是集合的元素需要是可排序的。

```
# Python3 program to convert a 
# set into a list
def convert(set):
    return sorted(set)

# Driver function
my_set = {1, 2, 3}

s = set(my_set)
print(convert(s))
```

**Output:**

```
[1, 2, 3]

```

**方法#3 :** 使用`[*set, ]`
这实际上是将列表文字中的集合 *s* 解包，该列表文字是由于单个逗号(，)的存在而创建的。这种方法速度稍快，但可读性较差。

```
# Python3 program to convert a 
# set into a list
def convert(set):
    return [*set, ]

# Driver function
s = set({1, 2, 3})
print(convert(s))
```

**Output:**

```
[1, 2, 3]

```