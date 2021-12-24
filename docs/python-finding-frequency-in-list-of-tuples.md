# Python |在元组列表中查找频率

> 原文:[https://www . geesforgeks . org/python-在元组列表中查找频率/](https://www.geeksforgeeks.org/python-finding-frequency-in-list-of-tuples/)

在 python 中，我们需要处理各种形式的数据，其中之一是元组列表，我们可能需要在其中执行任何类型的操作。这篇特别的文章讨论了寻找元组列表中第一个元素的频率的方法，元组列表可以扩展到任何索引。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`map() + count()`**
map 函数可以用来累加列表中所有元组的索引，计数频率的任务可以使用 python 库的泛型计数函数来完成。

```py
# Python3 code to demonstrate
# finding frequency in list of tuples
# using map() + count()

# initializing list of tuples
test_list = [('Geeks', 1), ('for', 2), ('Geeks', 3)]

# printing the original list
print ("The original list is : " + str(test_list))

# using map() + count()
# finding frequency in list of tuples 
res = list(map(lambda i : i[0], test_list)).count('Geeks')

# printing result
print ("The frequency of element is : " + str(res))
```

**Output:**

```py
The original list is : [('Geeks', 1), ('for', 2), ('Geeks', 3)]
The frequency of element is : 2

```

**方法 2:使用`Counter()` +列表理解**
列表理解执行获取元组首元素的任务，计数部分由集合库 Counter 函数处理。

```py
# Python3 code to demonstrate
# finding frequency in list of tuples
# using Counter() + list comprehension
from collections import Counter

# initializing list of tuples
test_list = [('Geeks', 1), ('for', 2), ('Geeks', 3)]

# printing the original list
print ("The original list is : " + str(test_list))

# using Counter() + list comprehension
# finding frequency in list of tuples 
res = Counter(i[0] for i in test_list)

# printing result
print ("The frequency of element is : " + str(res['Geeks']))
```

**Output:**

```py
The original list is : [('Geeks', 1), ('for', 2), ('Geeks', 3)]
The frequency of element is : 2

```