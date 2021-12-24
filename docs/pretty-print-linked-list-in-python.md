# Python 中的漂亮打印链表

> 原文:[https://www . geesforgeks . org/Pitty-print-linked-list-in-python/](https://www.geeksforgeeks.org/pretty-print-linked-list-in-python/)

创建自定义数据类型可能很棘手，尤其是当您想要像使用任何其他数据类型一样使用它时。链表可以看作是自定义数据类型的一个例子。在其他语言中，如果你想打印链表，你可以定义一个单独的打印函数，类似于 **pprint** ，但是看起来有点奇怪，对吗？就像让默认的**打印**功能做同样的事情很好，对吗？这就是 Python 的用武之地。Python 有一些神奇的方法叫做 [**邓德方法**](https://www.geeksforgeeks.org/dunder-magic-methods-python/) 。

## 邓德方法

邓德代表方法下的**双。基本上，任何以双下划线开头和结尾的方法都被称为**邓德**方法或**魔法**方法。und 方法的一个例子是 [**__init__**](https://www.geeksforgeeks.org/__init__-in-python/) 。一个类似的方法是 **__str__** ，我们将在本文中使用它。这种方法可以用于 Python 中的漂亮打印。**漂亮打印**无非是应用各种样式，格式化要打印的内容。在这里了解更多 dunder 方法[。](https://www.geeksforgeeks.org/dunder-magic-methods-python/)**

**__str__** 方法指定当使用标准的**打印**功能打印一个类时，应该从该类返回什么。使用这个概念，我们可以更好地表示自定义数据类型。下面是这种自定义表示的一个例子。请注意，重点是链表实现，但更多的是表示它的 pythonic 方式。

**示例:**俏丽打印单链表 **10- > 15- > 20** 作为**【10，15，20】**

## python 3

```
class Node:
    def __init__(self, val=None):
        self.val = val
        self.next = None

class LinkedList:
    def __init__(self, head=None):
        self.head = head

    def __str__(self):

        # defining a blank res variable
        res = ""

        # initializing ptr to head
        ptr = self.head

       # traversing and adding it to res
        while ptr:
            res += str(ptr.val) + ", "
            ptr = ptr.next

       # removing trailing commas
        res = res.strip(", ")

        # chen checking if 
        # anything is present in res or not
        if len(res):
            return "[" + res + "]"
        else:
            return "[]"

if __name__ == "__main__":

    # defining linked list
    ll = LinkedList()

    # defining nodes
    node1 = Node(10)
    node2 = Node(15)
    node3 = Node(20)

    # connecting the nodes
    ll.head = node1
    node1.next = node2
    node2.next = node3

    # when print is called, by default 
    #it calls the __str__ method
    print(ll)
```

**输出**

```
[10, 15, 20]

```

T17】

注意，打印类时，默认调用 **__str__** 。这就是 Python 的魔力。这篇文章的主要目的是展示小魔法方法是如何让你的生活变得容易得多的。