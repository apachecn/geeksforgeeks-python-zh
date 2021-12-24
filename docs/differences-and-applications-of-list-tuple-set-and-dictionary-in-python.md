# Python 中列表、元组、集合、字典的区别与应用

> 原文:[https://www . geeksforgeeks . org/python 中元组集和字典列表的差异和应用/](https://www.geeksforgeeks.org/differences-and-applications-of-list-tuple-set-and-dictionary-in-python/)

[**<u>列表:</u>**](https://www.geeksforgeeks.org/python-list/) 就像[动态大小的数组](https://www.geeksforgeeks.org/how-do-dynamic-arrays-work/)，用其他语言声明(C++中的[vector](https://www.geeksforgeeks.org/vector-in-cpp-stl/)和 Java 中的[ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/))。列表不必总是同质的，这使得它成为 [Python](https://www.geeksforgeeks.org/python-programming-language/) 中最强大的工具。

[**<u>元组:</u>**](https://www.geeksforgeeks.org/tuples-in-python/) 元组是用逗号分隔的 Python 对象的集合。在某些方面，元组在索引、嵌套对象和重复方面类似于列表，但是元组是不可变的，不像列表是可变的。

[**<u>集合:</u>**](https://www.geeksforgeeks.org/sets-in-python/) 集合是一种无序的集合数据类型，它是可迭代的、可变的，并且没有重复的元素。Python 的集合类代表了集合的数学概念。

[**<u>Dictionary:</u>**](https://www.geeksforgeeks.org/python-dictionary/)**在 Python 中是一个无序的数据值集合，用于像地图一样存储数据值，与其他只保存单个值作为元素的数据类型不同，Dictionary 保存 **key:value** pair。字典中提供了键值，以使其更加优化。**

**列表、元组、集合和字典是 python 中的数据结构，用于以高效的方式存储和组织数据。**

<figure class="table">

| **列表** | **元组** | **设置** | **词典** |
| 列表是一种非同构数据结构，它将元素存储在单行和多行多列中 | 元组也是非同构数据结构，它存储单行和多行多列 | 集合数据结构也是非同构数据结构，但存储在单行中 | 字典也是一种存储键值对的非同构数据结构 |
| 列表可以用[ ]表示 | 元组可以表示为( ) | 集合可以用{ }表示 | 字典可以用{ }表示 |
| 列表允许重复元素 | 元组允许重复元素 | 集合不允许重复元素 | 集合不允许重复元素，字典不允许重复键。 |
| 列表可以使用嵌套在所有 | 元组可以使用嵌套在所有 | 集合可以使用嵌套在所有 | 字典可以使用嵌套在所有 |
| 示例:[1，2，3，4，5] | 示例:(1，2，3，4，5) | 示例:{1，2，3，4，5} | 示例:{1，2，3，4，5} |
| 可以使用 **list()** 功能创建列表 | 可以使用**元组()**函数创建元组。 | 可以使用 **set()** 功能创建集合 | 可以使用 **dict()** 功能创建字典。 |
| 列表是可变的，即我们可以对列表进行任何更改。 | 元组是不可变的，即我们不能对元组进行任何更改 | 集合是可变的，即我们可以对集合进行任何更改。但是元素是不重复的。 | 字典是可变的。但是密钥是不重复的。 |
| 列表已排序 | 元组是有序的 | 集合是无序的 | 字典是有序的 |
| 创建空列表l=[] | 创建空元组t=()

 | 创建集合a=set()b =设置(a) | 创建空字典d={} |

</figure>

**下面是实现列表、元组、集合和字典的程序:**

## **蟒蛇 3**

```py
# Python3 program for explaining
# use of list, tuple, set and 
# dictionary

# Lists
l = []

# Adding Element into list
l.append(5)
l.append(10)
print("Adding 5 and 10 in list", l)

# Popping Elements from list
l.pop()
print("Popped one element from list", l)
print()

# Set
s = set()

# Adding element into set
s.add(5)
s.add(10)
print("Adding 5 and 10 in set", s)

# Removing element from set
s.remove(5)
print("Removing 5 from set", s)
print()

# Tuple
t = tuple(l)

# Tuples are immutable
print("Tuple", t)
print()

# Dictionary
d = {}

# Adding the key value pair
d[5] = "Five"
d[10] = "Ten"
print("Dictionary", d)

# Removing key-value pair
del d[10]
print("Dictionary", d)
```

****Output**

```py
Adding 5 and 10 in list [5, 10]
Popped one element from list [5]

Adding 5 and 10 in set {10, 5}
Removing 5 from set {10}

Tuple (5,)

Dictionary {5: 'Five', 10: 'Ten'}
Dictionary {5: 'Five'}
```** 

### **列表、集合、元组和字典的应用**

****列表:****

*   **以 JSON 格式使用**
*   **对阵列操作有用**
*   **用于数据库**

****元组:****

*   **用于一次通过 SQL 查询在数据库中插入记录
    Ex: (1。sravan '，34)。(2.‘极客’，35)** 
*   **用于括号检查器**

****设置****

*   **寻找独特的元素**
*   **加入操作**

****词典****

*   **用于创建带有列表的数据框**
*   **用于 JSON**