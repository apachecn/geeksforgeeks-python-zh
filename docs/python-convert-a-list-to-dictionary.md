# Python |将列表转换为词典

> 原文:[https://www . geesforgeks . org/python-convert-a-list-to-dictionary/](https://www.geeksforgeeks.org/python-convert-a-list-to-dictionary/)

给定一个列表，编写一个 Python 程序，将给定的列表转换成字典，这样所有奇数元素都有键，偶数元素都有值。由于 python 字典是无序的，所以输出可以是任何顺序。
**例:**

```
Input : ['a', 1, 'b', 2, 'c', 3]
Output : {'a': 1, 'b': 2, 'c': 3}

Input : ['Delhi', 71, 'Mumbai', 42]
Output : {'Delhi': 71, 'Mumbai': 42}

```

**方法#1 :** 字典理解
要将列表转换为字典，我们可以使用列表理解并制作一个关键字:连续元素的值对。最后，将列表键入*字典*类型。

## 蟒蛇 3

```
# Python3 program to Convert a
# list to dictionary

def Convert(lst):
    res_dct = {lst[i]: lst[i + 1] for i in range(0, len(lst), 2)}
    return res_dct

# Driver code
lst = ['a', 1, 'b', 2, 'c', 3]
print(Convert(lst))
```

**Output**

```
{'a': 1, 'b': 2, 'c': 3}

```

**方法#2 :** 使用 *zip()* 方法
首先创建一个迭代器，并将其初始化为变量“it”。然后用*压缩*的方法，将键和值压缩在一起。最后打成*字*字。

## 蟒蛇 3

```
# Python3 program to Convert a
# list to dictionary

def Convert(a):
    it = iter(a)
    res_dct = dict(zip(it, it))
    return res_dct

# Driver code
lst = ['a', 1, 'b', 2, 'c', 3]
print(Convert(lst))
```

**Output**

```
{'a': 1, 'b': 2, 'c': 3}

```