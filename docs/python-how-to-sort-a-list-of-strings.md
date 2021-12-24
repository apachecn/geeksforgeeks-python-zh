# Python |如何对字符串列表进行排序

> 原文:[https://www . geesforgeks . org/python-如何对字符串列表进行排序/](https://www.geeksforgeeks.org/python-how-to-sort-a-list-of-strings/)

给定一个字符串列表，任务是根据给定的需求对该列表进行排序。

在对 sting 列表进行排序时，可能会出现多种情况，例如–

*   按字母/反向顺序排序。
*   基于字符串的长度
*   对字符串等列表中的整数值进行排序。

让我们讨论执行这项任务的各种方法。

**示例#1:** 使用`sort()`功能。

```py
# Python program to sort a list of strings

lst = ['gfg', 'is', 'a', 'portal', 'for', 'geeks']

# Using sort() function
lst.sort()

print(lst)
```

**Output:**

```py
['a', 'for', 'geeks', 'gfg', 'is', 'portal']

```

**例 2:** 使用`sorted()`功能。

```py
# Python program to sort a list of strings

lst = ['gfg', 'is', 'a', 'portal', 'for', 'geeks']

# Using sorted() function
for ele in sorted(lst):
    print(ele)
```

**Output:**

```py
a
for
geeks
gfg
is
portal

```

**例 3:** 按字符串长度排序

```py
# Python program to sort a list of strings

lst = ['Geeksforgeeks', 'is', 'a', 'portal', 'for', 'geeks']

# Using sort() function with key as len
lst.sort(key = len)

print(lst)
```

**Output:**

```py
['a', 'is', 'for', 'geeks', 'portal', 'Geeksforgeeks']

```

**示例#4:** 按整数值对字符串进行排序

```py
# Python program to sort a list of strings

lst = ['23', '33', '11', '7', '55']

# Using sort() function with key as int
lst.sort(key = int)

print(lst)
```

**Output:**

```py
['7', '11', '23', '33', '55']

```

**示例#5:** 按降序排序

```py
# Python program to sort a list of strings

lst = ['gfg', 'is', 'a', 'portal', 'for', 'geeks']

# Using sort() function
lst.sort(reverse = True)

print(lst)
```

**Output:**

```py
['portal', 'is', 'gfg', 'geeks', 'for', 'a']

```