# Python |组块元组到 N

> 原文:[https://www.geeksforgeeks.org/python-chunk-tuples-to-n/](https://www.geeksforgeeks.org/python-chunk-tuples-to-n/)

有时，在处理数据时，我们可能会遇到一个问题，即我们可能需要对大小为 n 的元组执行分块。这在我们需要分块提供数据的应用程序中很流行。让我们讨论执行这项任务的某些方法。
**方法#1:使用列表理解**
这是执行这个任务的蛮力和速记方法。在这种情况下，我们一次拆分 N 个元素，并为它们构建一个新的元组。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Chunk Tuples to N
# using list comprehension

# initialize tuple
test_tup = (10, 4, 5, 6, 7, 6, 8, 3, 4)

# printing original tuple
print("The original tuple : " + str(test_tup))

# initialize N
N = 3

# Chunk Tuples to N
# using list comprehension
res = [test_tup[i : i + N] for i in range(0, len(test_tup), N)]

# printing result
print("The tuples after chunking are : " + str(res))
```

**Output : **

```
The original tuple : (10, 4, 5, 6, 7, 6, 8, 3, 4)
The tuples after chunking are : [(10, 4, 5), (6, 7, 6), (8, 3, 4)]
```

**方法 2:使用 zip() + iter()**
以上功能的组合也可以用来解决这个问题。在本文中，我们使用 zip()来组合组块，iter()转换成合适的格式。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Chunk Tuples to N
# using zip() + iter()

# initialize tuple
test_tup = (10, 4, 5, 6, 7, 6, 8, 3, 4)

# printing original tuple
print("The original tuple : " + str(test_tup))

# initialize N
N = 3

# Chunk Tuples to N
# using zip() + iter()
temp = [iter(test_tup)] * N
res = list(zip(*temp))

# printing result
print("The tuples after chunking are : " + str(res))
```

**Output : **

```
The original tuple : (10, 4, 5, 6, 7, 6, 8, 3, 4)
The tuples after chunking are : [(10, 4, 5), (6, 7, 6), (8, 3, 4)]
```