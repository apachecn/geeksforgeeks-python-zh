# Python 中的 Pygorithm 模块

> 原文:[https://www.geeksforgeeks.org/pygorithm-module-in-python/](https://www.geeksforgeeks.org/pygorithm-module-in-python/)

[Pygorithm 模块](http://pygorithm.readthedocs.io/en/latest/)是一个纯 Python 编写的 Python 模块，仅用于教育目的。只需导入所需的算法，就可以获得代码、时间复杂度等更多信息。这是开始学习 Python 编程和理解概念的好方法。Pygorithm 模块还可以帮助学习 Python 语言中所有主要算法的实现。

要安装 Pygorithm 模块:

```
pip3 install pygorithm
```

示例:

```
# import the required data structure
from pygorithm.data_structures import stack

# create a stack with default stack size 10
myStack = stack.Stack()

# push elements into the stack
myStack.push(2)
myStack.push(5)
myStack.push(9)
myStack.push(10)

# print the contents of stack
print(myStack)

# pop elements from stack
myStack.pop()
print(myStack)

# peek element in stack
print(myStack.peek())

# size of stack
print(myStack.size())
```

**输出:**

```
2 5 9 10
2 5 9
9
3

```

要查看一个模块中所有可用的功能，只需以模块名称作为参数键入 **`help()`** 。

```
# Help on package pygorithm.data_structures
help(data_structures)
```

**输出:**

```
NAME
    pygorithm.data_structures - Collection of data structure examples

PACKAGE CONTENTS
    graph
    heap
    linked_list
    quadtree
    queue
    stack
    tree
    trie

DATA
    __all__ = ['graph', 'heap', 'linked_list', 'queue', 'stack', 'tree', '...

```

使用 get_code()获取这些数据结构的代码。

```
# to get code for BinarySearchTree
BStree = tree.BinarySearchTree.get_code()

print(BStree)
```

**输出:**

```
class BinarySearchTree(object):

    def __init__(self):
        self.root = None

    def insert(self, data):
        """
        inserts a node in the tree
        """
        if self.root:
            return self.root.insert(data)
        else:
            self.root = BSTNode(data)
            return True

    def delete(self, data):
        """
        deletes the node with the specified data from the tree
        """
        if self.root is not None:
            return self.root.delete(data)

    def find(self, data):
        if self.root:
            return self.root.find(data)
        else:
            return False

    def preorder(self):
        """
        finding the preorder of the tree
        """
        if self.root is not None:
            return self.root.preorder(self.root)

    def inorder(self):
        """
        finding the inorder of the tree
        """
        if self.root is not None:
            return self.root.inorder(self.root)

    def postorder(self):
        """
        finding the postorder of the tree
        """
        if self.root is not None:
            return self.root.postorder(self.root)

    @staticmethod
    def get_code():
        """
        returns the code of the current class
        """
        return inspect.getsource(BinarySearchTree)
```

获取以下脚本的复杂性:

```
# create a stack with default stack size 10
Bsort = sorting.bubble_sort.time_complexities()
```

**输出:**

```
Best Case: O(n), Average Case: O(n ^ 2), Worst Case: O(n ^ 2).

For Improved Bubble Sort:
Best Case: O(n); Average Case: O(n * (n - 1) / 4); Worst Case: O(n ^ 2)

```

[Pygorithm 源代码快速链接](https://github.com/OmkarPathak/pygorithm)