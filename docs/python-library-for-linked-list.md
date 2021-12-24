# 链表 Python 库

> 原文:[https://www . geesforgeks . org/python-library-for-link-list/](https://www.geeksforgeeks.org/python-library-for-linked-list/)

[**链表**](https://www.geeksforgeeks.org/data-structures/linked-list/) 是编程中简单的数据结构，显然是用来存储数据并进行相应的检索。为了更容易想象，它更像一个动态数组，其中数据元素通过指针链接(即当前记录指向它的下一个记录，下一个记录指向它后面的记录，这一直持续到结构的末尾)，而不是被紧密打包。
链表有两种类型:

1.  单链表:在这种情况下，节点指向紧接其后的节点
2.  双向链表:在这种情况下，节点不仅引用它旁边的节点，还引用它前面的节点。

## **Python 中的链表:**

从 Python 开始，它没有像经典编程语言那样内置链表库。Python 确实有一个作为动态数组工作的内置类型列表，但是它的操作不应该与链表的典型功能相混淆。这并不意味着人们不能在 Python 中实现链表，他们可以，但它不会是直截了当的。以下方法可用于在 Python 中实现链表，因为它没有内置库:

**方法一:**使用 [**得克()**](https://www.geeksforgeeks.org/deque-in-python/) 包裹。
这是 Python 中的一个内置类，显然是用于出列的，但是可以通过某种方式实现，使得它在特定条件下像链表一样工作。

下面是链表的实现:

## 蟒蛇 3

```py
# importing module
import collections

# initialising a deque() of arbitrary length
linked_lst = collections.deque()

# filling deque() with elements
linked_lst.append('first')
linked_lst.append('second')
linked_lst.append('third')

print("elements in the linked_list:")
print(linked_lst)

# adding element at an arbitrary position
linked_lst.insert(1, 'fourth')

print("elements in the linked_list:")
print(linked_lst)

# deleting the last element
linked_lst.pop()

print("elements in the linked_list:")
print(linked_lst)

# removing a specific element
linked_lst.remove('fourth')

print("elements in the linked_list:")
print(linked_lst)
```

**输出:**

```py
elements in the linked_list:
deque(['first', 'second', 'third'])
elements in the linked_list:
deque(['first', 'fourth', 'second', 'third'])
elements in the linked_list:
deque(['first', 'fourth', 'second'])
elements in the linked_list:
deque(['first', 'second'])
```

**什么时候用 deque()做链表？**

*   只需要在前面和后面分别插入和删除元素。从中间插入和移除元素变得很耗时。
*   原地反转，因为 Python 现在允许元素在原地反转。
*   存储优于性能，并非所有元素都有自己的独立节点

**方法二:**使用 **llist** 套装。

**llist** 是 CPython 提供基本链表数据结构的扩展模块。命令行中的命令下面给出了类型:

```py
pip install llist
```

下面是链表的实现:

## 蟒蛇 3

```py
# importing packages
import llist
from llist import sllist,sllistnode

# creating a singly linked list
lst = sllist(['first','second','third'])
print(lst)
print(lst.first)
print(lst.last)
print(lst.size)
print()

# adding and inserting values
lst.append('fourth')
node = lst.nodeat(2)

lst.insertafter('fifth',node)

print(lst)
print(lst.first)
print(lst.last)
print(lst.size)
print()

# poping a value
#i.e. removing the last entry
# of the list
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

```py
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

**方法 3:** 使用**结构链接**包

结构链接用于轻松访问和可视化不同的数据结构，包括链表、双链表、二叉树、图、栈和队列。

结构链接。LinkedList 和 structlinks。DoublyLikedList 模块可以用来制作链表。所有可以用列表执行的操作也可以用 structlinks 执行。LinkedList 类。

碰杯去[文档](https://eeshannarula29.github.io/structlinks/)

在命令行中键入命令:

```py
pip install structlinks
```

下面是链表的一些方法的实现:

## 蟒蛇 3

```py
import structlinks
from structlinks import LinkedList

# create an empty linked list
lst = LinkedList()

# create a linked list with initial values
lst = LinkedList([1, 10.0, 'string'])

print(lst)

print()

print('Elements of list:')

# elements of the list
element0 = lst[0]
element1 = lst[1]
element2 = lst[2]

print(f'first element : {element0}')
print(f'second element : {element1 }')
print(f'third element : {element2}')

print()

print('Length of list:')

# Length of the list
length = len(lst)

print(f'size of the list : {length}')

print()

print('Set item:')

# Set item
lst[0] = 10

print(f'list after setting lst[0] to 10 : {lst}')

print()

print('Append And Insert:')

# Append And Insert
lst.append('another string')
lst.insert(1, 0.0)

print(f'list after appedning and inserting: {lst}')

print()

print('Pop and Remove')

# Pop and Remove
element = lst.pop(0)
lst.remove(10.0)

print(f'list after poping and removing : {lst}')
print(f'pop function also returns the element : {element}')

# This code is contributed by eeshannarula29
```

**输出:**

```py
[1 -> 10.0 -> string]

Elements of list:
1
10.0
string

Length of list:
3

Set item:
list after setting lst[0] to 10 : [10 -> 10.0 -> string]

Append and Insert:
list after appedning and inserting: [10 -> 0.0 -> 10 -> string -> another string]

Pop and Remove:
list after poping and removing: [0.0 -> string -> another string]
```