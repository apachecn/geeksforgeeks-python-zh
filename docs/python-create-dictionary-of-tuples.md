# Python–创建元组字典

> 原文:[https://www . geeksforgeeks . org/python-create-dictionary-of-tuples/](https://www.geeksforgeeks.org/python-create-dictionary-of-tuples/)

在本文中，我们将讨论如何在 Python 中创建元组字典。

## 以元组为关键字的元组字典

这里我们将在字典中以元组的形式传递关键字

**语法:**

```
{(tuple1):value,(tuple2):value,.........,(tuple3):value}
```

这里，元组是作为某个值的关键字的元素的集合

**示例:** Python 程序，创建以元组为关键字的元组字典

## 蟒蛇 3

```
# tuple of favourite food as key
# value is name of student
data = {("chapathi", "roti"): 'Bobby', 
        ("Paraota", "Idly", "Dosa"): 'ojaswi'}

# display
data
```

**输出:**

```
{('Paraota', 'Idly', 'Dosa'): 'ojaswi', ('chapathi', 'roti'): 'Bobby'}
```

## 以元组为值的元组字典

这里我们将在字典中以元组的形式传递值

**语法:**

```
{key:(tuple),key :(tuple2).........,key:(tuple)}
```

这里，元组是表示某个键的某个值的元素的集合。

**示例:** Python 程序，创建以元组为值的元组字典

## 蟒蛇 3

```
# tuple of favourite food as value
# key is name of student
data = {'Bobby': ("chapathi", "roti"), 
        'ojaswi': ("Paraota", "Idly", "Dosa")}

# display
data
```

**输出:**

```
{'Bobby': ('chapathi', 'roti'), 'ojaswi': ('Paraota', 'Idly', 'Dosa')}
```

## 从元组创建字典

在这里，我们将从嵌套元组中创建一个字典，为此，我们需要在每个元组中传递两个值，一个表示键，另一个表示字典中的对应值。

**语法:**

```
dict((value, key) for key,value in nested_tuple)
```

**示例:**从元组创建字典

## 蟒蛇 3

```
# one value is age of student
# second value is student name
data = ((24, "bobby"), (21, "ojsawi"))

# convert into dictionary
final = dict((value, key) for key, value in data)

# display
print(final)
```

**输出:**

```
{'bobby': 24, 'ojsawi': 21}
```