# Python |以索引为值的字典

> 原文:[https://www . geeksforgeeks . org/python-以索引为值的字典/](https://www.geeksforgeeks.org/python-dictionary-with-index-as-value/)

数据类型之间的相互转换非常流行，因此已经写了许多文章来演示不同类型的问题及其解决方案。本文讨论了将列表转换为字典的另一个类似类型的问题，将值作为元素出现的索引。让我们讨论一下解决这个问题的某些方法。

**方法一:利用字典理解+ `enumerate()`**

使用上述函数的组合可以很容易地解决这个问题，字典理解可以执行构造字典的任务，枚举函数可以用来访问索引值和元素。

```py
# Python3 code to demonstrate
# Dictionary with index as value
# using Dictionary comprehension + enumerate()

# initializing list
test_list = ['Nikhil', 'Akshat', 'Akash', 'Manjeet']

# printing original list
print("The original list : " + str(test_list))

# using Dictionary comprehension + enumerate()
# Dictionary with index as value
res = {val : idx + 1 for idx, val in enumerate(test_list)}

# print result
print("The Dictionary after index keys : " + str(res))
```

**Output :**

```py
The original list : ['Nikhil', 'Akshat', 'Akash', 'Manjeet']
The Dictionary after index keys : {'Akshat': 2, 'Nikhil': 1, 'Manjeet': 4, 'Akash': 3}

```

**方法 2:使用`dict() + zip()`**

这个问题也可以通过以上两个函数的组合来解决，dict 方法可以用来转换成字典，zip 函数可以用来映射索引和关键字。

```py
# Python3 code to demonstrate
# Dictionary with index as value
# using dict() + zip()

# initializing list
test_list = ['Nikhil', 'Akshat', 'Akash', 'Manjeet']

# printing original list
print("The original list : " + str(test_list))

# using dict() + zip()
# Dictionary with index as value
res = dict(zip(test_list, range(1, len(test_list)+1)))

# print result
print("The Dictionary after index keys : " + str(res))
```

**Output :**

```py
The original list : ['Nikhil', 'Akshat', 'Akash', 'Manjeet']
The Dictionary after index keys : {'Akshat': 2, 'Nikhil': 1, 'Manjeet': 4, 'Akash': 3}

```