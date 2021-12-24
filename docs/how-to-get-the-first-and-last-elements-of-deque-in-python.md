# 如何获取 Python 中得克的首末元素？

> 原文:[https://www . geesforgeks . org/如何获取 python 中的第一个和最后一个元素/](https://www.geeksforgeeks.org/how-to-get-the-first-and-last-elements-of-deque-in-python/)

Deque 是一个双端队列，使用 Python 中的[集合](https://www.geeksforgeeks.org/python-collections-module/)模块实现。让我们来看看如何在一个德格中获得第一个和最后一个值。

**方法 1:** 通过元素的索引访问元素。

collections 模块中的 deque 数据结构没有 peek 方法，但是通过获取带方括号的元素可以获得类似的结果。第一个元素可以使用[0]访问，最后一个元素可以使用[-1]访问。

## 蟒蛇 3

```py
# importing the module
from collections import deque  

# creating a deque  
dq = deque(['Geeks','for','Geeks', 'is', 'good'])   

# displaying the deque
print(dq)

# fetching the first element
print(dq[0])

# fetching the last element
print(dq[-1])
```

**输出:**

```py
deque(['Geeks', 'for', 'Geeks', 'is', 'good'])
Geeks
good

```

**方法 2:** 使用 **popleft()** 和 **pop()** 方法

popleft()方法用于从队列左侧弹出第一个元素或元素，pop()方法用于从队列右侧弹出最后一个元素或元素。需要注意的是，这些方法也会从 deque 中删除元素，所以当目标是只获取第一个和最后一个元素时，它们不应该是首选的。

## 蟒蛇 3

```py
# importing the module
from collections import deque  

# creating a deque  
dq = deque(['Geeks','for','Geeks', 'is', 'good'])   

# displaying the deque
print(dq)

# fetching and deleting the first element
print(dq.popleft())

# fetching and deleting the last element
print(dq.pop())

# displaying the deque
print(dq)
```

**输出:**

```py
deque(['Geeks', 'for', 'Geeks', 'is', 'good'])
Geeks
good
deque(['for', 'Geeks', 'is'])

```