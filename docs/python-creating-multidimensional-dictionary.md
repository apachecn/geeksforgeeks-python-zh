# Python |创建多维词典

> 原文:[https://www . geesforgeks . org/python-creating-多维-dictionary/](https://www.geeksforgeeks.org/python-creating-multidimensional-dictionary/)

有时候，在使用 Python 字典时，我们需要嵌套字典。但问题是，我们必须在初始化嵌套字典中的值之前声明。让我们通过本文中讨论的方法来解决这个特殊的问题。

**方法#1:使用 setdefault()**
该函数用于在字典的第一嵌套层定义一个空字典，使其成为 2D。在这种情况下，不需要在字典级别定义显式字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Creating Multidimensional dictionary
# Using setdefault()

# Initialize dictionary
test_dict = {}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Using setdefault()
# Creating Multidimensional dictionary
test_dict.setdefault(1, {})[4] = 7

# printing result
print("Dictionary after nesting : " + str(test_dict))
```

**Output : **

```py
The original dictionary : {}
Dictionary after nesting : {1: {4: 7}}
```

**方法 2:使用 defaultdict()**
可以使用 defaultdict()实现多嵌套的创建。不仅在一个层次上，而且在 N 个层次上，嵌套都可以用这个来实现。缺点是它创建了 defaultdict 对象。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Creating Multidimensional dictionary
# Using defaultdict()
from collections import defaultdict

# Utility function to create dictionary
def multi_dict(K, type):
    if K == 1:
        return defaultdict(type)
    else:
        return defaultdict(lambda: multi_dict(K-1, type))

# Initialize dictionary
test_dict = {}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Using defaultdict()
# Creating Multidimensional dictionary
# calling function
test_dict = multi_dict(3, int)
test_dict[2][3][4] = 1

# printing result
print("Dictionary after nesting : " + str(dict(test_dict)))
```

**Output : **

```py
The original dictionary : {}
Dictionary after nesting : {2: defaultdict(<function multi_dict.<locals>.<lambda> at 0x7f8707a54158>, {3: defaultdict(<class 'int'>, {4: 1})})}
```