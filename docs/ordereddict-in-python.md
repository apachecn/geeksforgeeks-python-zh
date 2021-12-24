# Python 中的 ordereddct

> 原文:[https://www.geeksforgeeks.org/ordereddict-in-python/](https://www.geeksforgeeks.org/ordereddict-in-python/)

一个 **OrderedDict** 是一个字典子类，它会记住首次插入键的顺序。 [dict()](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/) 和 OrderedDict()之间唯一的区别是:

OrderedDict **保留插入键的顺序**。常规字典不跟踪插入顺序，迭代它会以任意顺序给出值。相比之下，项目的插入顺序由 OrderedDict 记住。

## 计算机编程语言

```py
# A Python program to demonstrate working of OrderedDict
from collections import OrderedDict

print("This is a Dict:\n")
d = {}
d['a'] = 1
d['b'] = 2
d['c'] = 3
d['d'] = 4

for key, value in d.items():
    print(key, value)

print("\nThis is an Ordered Dict:\n")
od = OrderedDict()
od['a'] = 1
od['b'] = 2
od['c'] = 3
od['d'] = 4

for key, value in od.items():
    print(key, value)
```

输出:

```py
This is a Dict:
('a', 1)
('c', 3)
('b', 2)
('d', 4)

This is an Ordered Dict:
('a', 1)
('b', 2)
('c', 3)
('d', 4)
```

**要点:**

**1。键值变化:**如果某个键的值发生变化，则该键在 OrderedDict 中的位置保持不变。

## 计算机编程语言

```py
# A Python program to demonstrate working of key
# value change in OrderedDict
from collections import OrderedDict

print("Before:\n")
od = OrderedDict()
od['a'] = 1
od['b'] = 2
od['c'] = 3
od['d'] = 4
for key, value in od.items():
    print(key, value)

print("\nAfter:\n")
od['c'] = 5
for key, value in od.items():
    print(key, value)
```

输出:

```py
Before:

('a', 1)
('b', 2)
('c', 3)
('d', 4)

After:

('a', 1)
('b', 2)
('c', 5)
('d', 4)
```

**2。删除并重新插入**:删除并重新插入同一个键会将其按顺序推到后面，但是会保持插入的顺序。

## 计算机编程语言

```py
# A Python program to demonstrate working of deletion
# re-insertion in OrderedDict
from collections import OrderedDict

print("Before deleting:\n")
od = OrderedDict()
od['a'] = 1
od['b'] = 2
od['c'] = 3
od['d'] = 4

for key, value in od.items():
    print(key, value)

print("\nAfter deleting:\n")
od.pop('c')
for key, value in od.items():
    print(key, value)

print("\nAfter re-inserting:\n")
od['c'] = 3
for key, value in od.items():
    print(key, value)
```

输出:

```py
Before deleting:

('a', 1)
('b', 2)
('c', 3)
('d', 4)

After deleting:

('a', 1)
('b', 2)
('d', 4)

After re-inserting:

('a', 1)
('b', 2)
('d', 4)
('c', 3)
```

**其他注意事项**:

*   Python 版本中的有序字典比普通字典消耗更多的内存。这是因为底层的双链表实现保持了顺序。在 Python 2.7 中，有序字典不是字典子类，而是集合模块中的一个专用容器。
*   从 Python 3.7 开始，保证 Python 字典的插入顺序。
*   借助 *popitem* 功能，有序字典可以作为堆栈使用。尝试使用有序字典实现 LRU 缓存。

本文由**斯里·桑凯·乌帕拉帕蒂**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。