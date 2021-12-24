# Python |将字符串转换为 N 个组块元组

> 原文:[https://www . geesforgeks . org/python-convert-string-to-n-chunks-tuple/](https://www.geeksforgeeks.org/python-convert-string-to-n-chunks-tuple/)

有时，在使用 Python Strings 时，我们可能会遇到一个问题，需要将一个字符串分解成 N 个大小的块，再分解成一个元组。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+元组**
这是可以执行该任务的一种方法。在这种情况下，我们只需迭代字符串并分解字符串块，然后在一个线性中使用 tuple()构造元组。

```
# Python3 code to demonstrate working of
# Convert String to N chunks tuple
# Using list comprehension + tuple()

# initialize string
test_string = "ggggffffgggg"

# printing original string
print("The original string : " + str(test_string))

# initialize N 
N = 4

# Convert String to N chunks tuple
# Using list comprehension + tuple()
res = tuple(test_string[ i : i + N] for i in range(0, len(test_string), N))

# printing result
print("Chunked String into tuple : " + str(res))
```

**Output :**

```
The original string : ggggffffgggg
Chunked String into tuple : ('gggg', 'ffff', 'gggg')

```