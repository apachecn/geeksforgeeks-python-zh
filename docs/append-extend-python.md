# 在 Python 中追加()和扩展()

> 原文:[https://www.geeksforgeeks.org/append-extend-python/](https://www.geeksforgeeks.org/append-extend-python/)

**[追加](https://www.geeksforgeeks.org/list-methods-python/) :** 将其参数作为单个元素添加到列表的末尾。名单的长度增加了一个。

```
syntax: 
# Adds an object (a number, a string or a 
# another list) at the end of my_list
my_list.append(object)

```

```
my_list = ['geeks', 'for']
my_list.append('geeks')
print my_list
```

输出:

```
['geeks', 'for', 'geeks']

```

**注:**列表是一个对象。如果将另一个列表追加到列表中，参数列表将是列表末尾的单个对象。

```
my_list = ['geeks', 'for', 'geeks']
another_list = [6, 0, 4, 1]
my_list.append(another_list)
print my_list
```

输出:

```
['geeks', 'for', 'geeks', [6, 0, 4, 1]]

```

**[extend()](https://www.geeksforgeeks.org/list-methods-python/) :** 迭代其参数，并将每个元素添加到列表中并扩展列表。列表的长度随着其参数中的元素数量而增加。

```
syntax: 
# Each element of an iterable gets appended 
# to my_list
my_list.extend(iterable) 

```

```
my_list = ['geeks', 'for']
another_list = [6, 0, 4, 1]
my_list.extend(another_list)
print my_list
```

输出:

```
['geeks', 'for', 6, 0, 4, 1]

```

**注意:**字符串是可迭代的，所以如果你用字符串扩展一个列表，当你迭代字符串时，你会附加每个字符。

```
my_list = ['geeks', 'for', 6, 0, 4, 1]
my_list.extend('geeks')
print my_list
```

输出:

```
['geeks', 'for', 6, 0, 4, 1, 'g', 'e', 'e', 'k', 's']

```

**时间复杂度:**
**追加**时间复杂度不变，即 O(1)。
**Extend** 的时间复杂度为 O(k)。其中 k 是需要添加的列表长度。