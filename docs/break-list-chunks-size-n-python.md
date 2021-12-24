# 在 Python 中将列表分成大小为 N 的块

> 原文:[https://www . geesforgeks . org/break-list-chunks-size-n-python/](https://www.geeksforgeeks.org/break-list-chunks-size-n-python/)

**方法 1:使用[*yield*](https://www.geeksforgeeks.org/use-yield-keyword-instead-return-keyword-python/https://www.geeksforgeeks.org/use-yield-keyword-instead-return-keyword-python/)**
[yield](https://www.geeksforgeeks.org/use-yield-keyword-instead-return-keyword-python/)关键字使函数能够在再次调用时从停止的地方恢复。这是与常规函数的关键区别。常规函数不能回到它停止的地方。yield 关键字帮助函数记住它的状态。当函数在暂停执行时转入一个值时，yield 使函数能够暂停和恢复。

```py
my_list = ['geeks', 'for', 'geeks', 'like',
           'geeky','nerdy', 'geek', 'love',
               'questions','words', 'life']

# Yield successive n-sized
# chunks from l.
def divide_chunks(l, n):

    # looping till length l
    for i in range(0, len(l), n): 
        yield l[i:i + n]

# How many elements each
# list should have
n = 5

x = list(divide_chunks(my_list, n))
print (x)
```

输出:

```py
[['geeks', 'for', 'geeks', 'like', 'geeky'], 
 ['nerdy', 'geek', 'love', 'questions', 'words'], 
 ['life']]

```

**方法二:使用列表理解**
[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)是一种用一行代码打破列表的优雅方式。

```py
my_list = [1, 2, 3, 4, 5,
              6, 7, 8, 9]

# How many elements each
# list should have
n = 4 

# using list comprehension
final = [my_list[i * n:(i + 1) * n] for i in range((len(my_list) + n - 1) // n )] 
print (final)
```

输出:

```py
[[1, 2, 3, 4], [5, 6, 7, 8], [9]]

```

**替代实施:**

```py
l = [1, 2, 3, 4, 5, 6, 7, 8, 9] 

# How many elements each 
# list should have 
n = 4

# using list comprehension 
x = [l[i:i + n] for i in range(0, len(l), n)] 
print(x)
```

输出:

```py
[[1, 2, 3, 4], [5, 6, 7, 8], [9]]

```