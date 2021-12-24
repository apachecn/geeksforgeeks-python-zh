# Python |统计列表中的真布尔

> 原文:[https://www . geesforgeks . org/python-count-true-booleans-in-a-list/](https://www.geeksforgeeks.org/python-count-true-booleans-in-a-list/)

给定一个布尔值列表，编写一个 Python 程序来查找给定列表中真实布尔值的数量。

**示例:**

```py
Input : [True, False, True, True, False]
Output : 3

Input : [False, True, False, True]
Output : 2

```

**方法#1 :** 使用列表理解

计算列表中真布尔的一个简单方法是使用列表理解。

```py
# Python3 program to count True booleans in a list

def count(lst):

    return sum(bool(x) for x in lst)

# Driver code
lst = [True, False, True, True, False]
print(count(lst))
```

**Output:**

```py
3

```

**方法 2 :** 使用`sum()`

```py
# Python3 program to count True booleans in a list

def count(lst):

    return sum(lst)

# Driver code
lst = [True, False, True, True, False]
print(count(lst))
```

**Output:**

```py
3

```

下面给出了使用*求和*的一个更加健壮和透明的方法。

```py
def count(lst):

    return sum(1 for x in lst if x)
```

**法#3 :** `count()`法

```py
# Python3 program to count True booleans in a list

def count(lst):

    return lst.count(True)

# Driver code
lst = [True, False, True, True, False]
print(count(lst))
```

**Output:**

```py
3

```

**方法#4 :** `filter()`

```py
# Python3 program to count True booleans in a list

def count(lst):

    return len(list(filter(None, lst)))

# Driver code
lst = [True, False, True, True, False]
print(count(lst))
```

**Output:**

```py
3

```