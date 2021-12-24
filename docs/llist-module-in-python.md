# Python 中的 llist 模块

> 原文:[https://www.geeksforgeeks.org/llist-module-in-python/](https://www.geeksforgeeks.org/llist-module-in-python/)

直到很长一段时间，Python 都没有办法执行链表数据结构。它确实支持列表，但是当使用它们作为链表的概念时会遇到许多问题，比如列表是刚性的，并且没有通过指针连接，因此占用了定义的内存空间，如果列表没有完全填满，甚至可能会浪费内存空间。事实上，为了克服列表带来的问题，Python 的出列数据结构也可以像链表一样工作。但是所有这些都因为**而被覆盖了。**

## Python 中的 llist 模块

llist 是 CPython 的扩展模块，提供了基本的链表结构。它们明显快于出列甚至标准列表。

### 装置

为了利用 llist 提供的优势，它必须像任何其他 python 扩展或模块一样使用 pip 进行安装。以下命令将完成这项工作。

```
pip install llist
```

如果不是这样，可以从[http://pypi.python.org/pypi](http://pypi.python.org/pypi)手动下载，然后解包资源，用“python setup.py install”编译。一旦模块成功安装，您只需要在需要时导入该模块。

### 提供的方法

目前，llist 提供以下两种类型的链表:

1.  **单链表(sllist)** :节点指向旁边节点的链表。
2.  **双向链表(dllist)** :一种链表，其中节点指向它后面的节点以及它前面的节点。

该模块包含以下对象:

*   **dllist :** 实现双链表的对象
*   **dllistnode :** 返回一个新的双向链表节点，可选初始化
*   **dllistiterator:**dllist 的迭代器对象
*   **sllist :** 实现单链表的对象
*   **sllistnode :** 单链表节点，可选初始化
*   **sllistiterator:**sllist 的迭代器对象

下面的例子将帮助你更好地理解。他们给出了关于执行 llist 支持的两种列表的基本想法:
**例 1:** sllist

```
# importing packages
import llist
from llist import sllist, sllistnode

# creating a linked list
lst = sllist(['first', 'second', 'third'])
print(lst)
print(lst.first)
print(lst.last)
print(lst.size)
print()

# adding and inserting values
lst.append('fourth')
node = lst.nodeat(2)
lst.insertafter('fifth', node)
print(lst)
print(lst.first)
print(lst.last)
print(lst.size)
print()

# poping a value
# i.e. removing the last entry of the list
lst.pop()
print(lst)
print(lst.first)
print(lst.last)
print(lst.size)
print()

# removing a specific element
node = lst.nodeat(1)
lst.remove(node)
print(lst)
print(lst.first)
print(lst.last)
print(lst.size)
print()
```

**输出:**

```
sllist([first, second, third])
sllistnode(first)
sllistnode(third)
3

sllist([first, second, third, fifth, fourth])
sllistnode(first)
sllistnode(fourth)
5

sllist([first, second, third, fifth])
sllistnode(first)
sllistnode(fifth)
4

sllist([first, third, fifth])
sllistnode(first)
sllistnode(fifth)
3

```

**示例 2:** dllist

```
# importing packages
import llist
from llist import dllist, dllistnode

# creating a linked list
lst = dllist(['first', 'second', 'third'])
print(lst)
print(lst.first)
print(lst.last)
print(lst.size)
print()

# adding and inserting values
lst.append('fourth')
node = lst.nodeat(2)
lst.extendleft(['fifth', 'sixth'])
new_node = dllistnode('seventh')
ref_node = lst.nodeat(2)
lst.insertnode(new_node, ref_node)

print(lst)
print(lst.first)
print(lst.last)
print(lst.size)
print()

# poping a value
# i.e. removing the last entry of the list
lst.pop()
print(lst)
print(lst.first)
print(lst.last)
print(lst.size)
print()

# removing a specific element
node = lst.nodeat(1)
lst.remove(node)
print(lst)
print(lst.first)
print(lst.last)
print(lst.size)
print()
```

**输出:**

```
dllist([first, second, third])
dllistnode(first)
dllistnode(third)
3

dllist([sixth, fifth, seventh, first, second, third, fourth])
dllistnode(sixth)
dllistnode(fourth)
7

dllist([sixth, fifth, seventh, first, second, third])
dllistnode(sixth)
dllistnode(third)
6

dllist([sixth, seventh, first, second, third])
dllistnode(sixth)
dllistnode(third)
5
```