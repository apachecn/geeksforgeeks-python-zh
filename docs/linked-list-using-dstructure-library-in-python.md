# Python 中使用数据结构库的链表

> 原文:[https://www . geesforgeks . org/linked-list-use-d structure-library-in-python/](https://www.geeksforgeeks.org/linked-list-using-dstructure-library-in-python/)

数据结构是一个 Python 库，用于创建类似[链表](https://www.geeksforgeeks.org/data-structures/linked-list/)、[栈](https://www.geeksforgeeks.org/stack-in-python/)、[队列](https://www.geeksforgeeks.org/queue-in-python/)、hashmap、tree 等数据结构。链表是一种线性数据结构，其中元素不存储在连续的内存位置。链表中的元素使用指针进行链接，如下图所示:

![](img/d97a233bf3c89e80c46e6a3193e851d6.png)

```
pip install dstructure

```

让我们看看如何使用这个库创建不同类型的链表。

**1。单链表**

单链表包含具有数据字段和“下一个”字段的节点，该字段指向节点行中的下一个节点。可以在单链表上执行的操作包括插入、删除和遍历。

## 蟒蛇 3

```
from dstructure.ll.SLL import SLL

obj = SLL()
obj.insert(10)  # insert 10 in linked list
obj.insert(20)  # insert 20 in linked list
obj.insert(30)  # insert 30 in linked list
obj.insert(40)  # insert 40 in linked list
obj.insert(50)  # insert 50 in linked list
obj.insert(60)  # insert 60 in linked list
obj.delete_f()  # delete first node in linked list
obj.delete_l()  # delete last node in linked list
obj.delete(20)  # delete the node which we pass and return True otherwise False
obj.getnodes()  # return all the node in linked list in list.
obj.print()       # print all the in this format 10 -> 30 -> 40
```

**输出:**

```
[30,40,50]
30 -> 40 -> 50

```

**2。双向链表。**

双向链表是一种链表，其中每个节点除了存储其数据之外还有两个链接。第一个链接指向列表中的上一个节点，第二个链接指向列表中的下一个节点。

## 蟒蛇 3

```
from dstructure.ll.DLL import DLL

obj = DLL()
obj.insert(10)  # insert 10 in linked list
obj.insert(20)  # insert 20 in linked list
obj.insert(30)  # insert 30 in linked list
obj.insert(40)  # insert 40 in linked list
obj.delete_f()  # delete first node in linked list
obj.delete_l()  # delete last node in linked list
obj.delete(20)  # delete the node which we pass and return True otherwise False
obj.getnodes()  # return all the node in linked list in list.
obj.print()       # print all the in this format 10 <-> 30 <-> 40
```

**输出:**

```
10 <-> 30 <-> 40

```

**3。单循环链表。**

在单链表中，为了访问链表的任何节点，我们从第一个节点开始遍历。如果我们位于列表中间的任何节点，则不可能访问给定节点之前的节点。这个问题可以通过稍微改变单链表的结构来解决。在单链表中，下一部分(指向下一个节点的指针)为空，如果我们利用这个链接指向第一个节点，那么我们就可以到达前面的节点。

## 蟒蛇 3

```
from dstructure.ll.SCLL import SCLL

obj = SCLL()
obj.insert(10)  # insert 10 in linked list
obj.insert(20)  # insert 20 in linked list
obj.insert(30)  # insert 30 in linked list
obj.insert(40)  # insert 40 in linked list
obj.delete_f()  # delete first node in linked list
obj.delete_l()  # delete last node in linked list
obj.delete(20)  # delete the node which we pass and return True otherwise False
obj.getnodes()  # return all the node in linked list in list.
obj.print()       # print all the in this format 10 -> 30 -> 40
```

**输出:**

```
10 -> 30 -> 40

```

**4。双循环链表。**

循环双向链表具有双向链表和循环链表的性质，其中两个连续的元素通过上一个和下一个指针链接或连接，最后一个节点通过下一个指针指向第一个节点，第一个节点也通过上一个指针指向最后一个节点。

## 蟒蛇 3

```
from dstructure.ll.DCLL import DCLL

obj = DCLL()
obj.insert(10)  # insert 10 in linked list
obj.insert(20)  # insert 20 in linked list
obj.insert(30)  # insert 30 in linked list
obj.insert(40)  # insert 40 in linked list
obj.delete_f()  # delete first node in linked list
obj.delete_l()  # delete last node in linked list
obj.delete(20)  # delete the node which we pass and return True otherwise False
obj.getnodes()  # return all the node in linked list in list.
obj.print()       # print all the in this format 10 <-> 30 <-> 40
```

**输出:**

```
10 <-> 30 <-> 40

```