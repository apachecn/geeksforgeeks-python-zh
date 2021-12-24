# Python–sorted()和 sort()

的区别

> 原文:[https://www . geeksforgeeks . org/python-分类和排序的区别/](https://www.geeksforgeeks.org/python-difference-between-sorted-and-sort/)

排序意味着根据元素上的比较运算符重新排列给定的元素序列。比较运算符用于决定元素在相应数据结构中的新顺序。

**例如:**下面的字符列表按照其 ASCII 值的递增顺序进行排序。也就是说，ASCII 值较小的字符将比 ASCII 值较大的字符放在第一位。

![python-sorting](img/b90e4ce3815d98e502c2f3b64042a8db.png)

在 Python 中，对任何序列进行排序都非常容易，因为它提供了内置的排序方法。两种这样的方法是`sorted()`和`sort()`。这两种方法用于排序，但在它们自己的方式上有很大的不同。让我们一个一个地看一看。

## 已排序()

`sorted()`方法按升序或降序对给定序列进行排序，并始终返回一个排序列表。这种方法不会影响原始序列。

> **语法:**已排序(可迭代，键，反向=假)
> 
> **参数:**
> **可迭代:**序列(列表、元组、字符串)或集合(字典、集合、frozenset)或任何其他需要排序的迭代器。
> **键(可选):**用作键或排序比较基础的功能。
> **反向(可选):**如果设置为真，则可迭代将按反向(降序)顺序排序，默认情况下设置为假。
> 
> **返回类型:**返回排序列表。

**例 1:**

```py
# Python program to demonstrate
# sorted()

L = [1, 2, 3, 4, 5]

print("Sorted list:")
print(sorted(L))

print("\nReverse sorted list:")
print(sorted(L, reverse = True))

print("\nOriginal list after sorting:")
print(L)
```

**输出:**

```py
Sorted list:
[1, 2, 3, 4, 5]

Reverse sorted list:
[5, 4, 3, 2, 1]

Original list after sorting:
[1, 2, 3, 4, 5]

```

**示例 2:** 对不同的数据类型进行排序

```py
# Python program to demonstrate
# sorted()

# List 
x = ['q', 'w', 'r', 'e', 't', 'y'] 
print(sorted(x)) 

# Tuple 
x = ('q', 'w', 'e', 'r', 't', 'y') 
print(sorted(x))

# String-sorted based on ASCII translations 
x = "python"
print(sorted(x)) 

# Dictionary 
x = {'q':1, 'w':2, 'e':3, 'r':4, 't':5, 'y':6} 
print(sorted(x)) 

# Set 
x = {'q', 'w', 'e', 'r', 't', 'y'} 
print(sorted(x))
```

**输出:**

```py
['e', 'q', 'r', 't', 'w', 'y']
['e', 'q', 'r', 't', 'w', 'y']
['h', 'n', 'o', 'p', 't', 'y']
['e', 'q', 'r', 't', 'w', 'y']
['e', 'q', 'r', 't', 'w', 'y']

```

#### 使用关键参数

这个可选的参数键接受一个函数作为它的值。这个键函数在排序之前转换每个元素，它接受值并返回 1 个值，然后在排序中使用该值而不是原始值。

**示例:**假设我们想要根据字符串的长度对其进行排序。这可以通过将`len()`函数作为值传递给关键参数来实现。下面是实现。

```py
# Python program to demonstrate
# sorted()

L = ['aaaa', 'bbb', 'cc', 'd']

# sorted without key parameter
print(sorted(L))
print()

# sorted with key parameter
print(sorted(L, key = len))
```

**输出:**

```py
['aaaa', 'bbb', 'cc', 'd']

['d', 'cc', 'bbb', 'aaaa']

```

## 排序()

`sort()`函数与 sorted()非常相似，但与 sorted 不同的是，它不返回任何内容，并且对原始序列进行更改。此外，sort()是 list 类的一种方法，只能用于列表。

> **语法:** List_name.sort(键，反向=False)
> 
> **参数:**
> **键:**用作排序比较键的函数。
> **反转:**如果为真，列表按降序排序。
> 
> **返回类型:**无

**例 1:**

```py
# Python program to demonstrate
# sort()

# List of Integers 
numbers = [1, 3, 4, 2] 

# Sorting list of Integers 
numbers.sort() 

print(numbers) 

# List of Floating point numbers 
decimalnumber = [2.01, 2.00, 3.67, 3.28, 1.68] 

# Sorting list of Floating point numbers 
decimalnumber.sort() 

print(decimalnumber) 

# List of strings 
words = ["Geeks", "For", "Geeks"] 

# Sorting list of strings 
words.sort() 

print(words) 
```

**输出:**

```py
[1, 2, 3, 4]
[1.68, 2.0, 2.01, 3.28, 3.67]
['For', 'Geeks', 'Geeks']

```

**例 2:** 倒序排序。

```py
# Python program to demonstrate
# sort()

# List of Integers 
numbers = [1, 3, 4, 2] 

# Sorting list of Integers 
numbers.sort(reverse = True) 

print(numbers) 

# List of Floating point numbers 
decimalnumber = [2.01, 2.00, 3.67, 3.28, 1.68] 

# Sorting list of Floating point numbers 
decimalnumber.sort(reverse = True) 

print(decimalnumber) 

# List of strings 
words = ["Geeks", "For", "Geeks"] 

# Sorting list of strings 
words.sort(reverse = True) 

print(words) 
```

**输出:**

```py
[4, 3, 2, 1]
[3.67, 3.28, 2.01, 2.0, 1.68]
['Geeks', 'Geeks', 'For']

```

**例 3:** 使用关键参数。

```py
# Python program to demonstrate sorting by user's 
# choice 

# function to return the second element of the 
# two elements passed as the parameter 
def sortSecond(val): 
    return val[1]  

# list1 to demonstrate the use of sorting  
# using using second key  
list1 = [(1, 2), (3, 3), (1, 1)] 

# sorts the array in ascending according to  
# second element 
list1.sort(key = sortSecond)  
print(list1) 

# sorts the array in descending according to 
# second element 
list1.sort(key = sortSecond, reverse = True) 
print(list1) 
```

**输出:**

```py
[(1, 1), (1, 2), (3, 3)]
[(3, 3), (1, 2), (1, 1)]

```