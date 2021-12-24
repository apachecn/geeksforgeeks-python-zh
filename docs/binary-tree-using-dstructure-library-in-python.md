# Python 中使用数据结构库的二叉树

> 原文:[https://www . geesforgeks . org/binary-tree-use-d structure-library-in-python/](https://www.geeksforgeeks.org/binary-tree-using-dstructure-library-in-python/)

**数据结构**包是一个处理数据结构和算法的 Python 库。在本文中，我们将讨论如何使用 Python 中的数据结构库实现二叉树并执行各种操作。

### **安装**

要安装数据结构，请打开终端并编写以下命令:

```
pip install dstructure
```

### **二叉树**

元素最多有两个子元素的树称为 [**二叉树**](https://www.geeksforgeeks.org/binary-tree-set-1-introduction/) 。由于二叉树中的每个元素只能有两个子元素，我们通常将它们命名为左右子元素。然而，数据结构库有助于直接实现二叉树。

二叉树节点包含以下部分。

1.  数据
2.  指向左边孩子的指针
3.  指向右边孩子的指针

![](img/51a393ae1e2d94d14b5067e96e884b40.png)

### 可用方法

让我们看看处理二叉树的不同方法。首先，我们将制作二叉树，然后应用所有的方法。

为了创建二叉树，我们首先导入 dstructure 模块，创建一个 BTree 类对象来初始化一个空的二叉树，并使用 insert()方法将节点插入到树中。下面是用于在二叉树上创建和执行各种操作的各种方法。

*   **insert(int_value):** 这个函数获取 int 值，并将该值添加到树中。

## 蟒蛇 3

```
# import module
from dstructure.BTree import BTree

# create class
obj=BTree(23)

# insert nodes
obj.insert(10) 
obj.insert(20) 
obj.insert(30) 
obj.insert(40) 

# display object
print(obj)
```

**输出:**

```
<dstructure.BTree.BTree object at 0x000001F02815B648>
```

*   **order(obj):**这个函数将一个对象作为输入，返回树的有序遍历。

## 蟒蛇 3

```
# return inorder in list
inorder = obj.inorder(obj)  
print(inorder)
```

**输出:**

```
[10, 20, 23, 30, 40]
```

*   **前序(obj):** 这个函数以一个对象为输入，返回树的前序遍历。

## 蟒蛇 3

```
# return preorder in list
preorder = obj.preorder(obj) 
print(preorder)
```

**输出:**

```
[23, 10, 20, 30, 40]
```

*   **后置(obj):** 这个函数以一个对象作为输入，返回树的后置遍历。

## 蟒蛇 3

```
# return postorder in list
postorder = obj.postorder(obj)  
print(postorder)
```

**输出:**

```
[20, 10, 40, 30, 23]
```

*   **get_bfs() :** 这个函数返回树的广度优先搜索遍历。

## 蟒蛇 3

```
# return Breadth First Search of tree in list
bfs = obj.get_bfs()  
print(bfs)
```

**输出:**

```
[23, 30, 10, 40, 20]
```

*   **get_dfs():** 这个函数返回树的深度优先搜索遍历。

## 蟒蛇 3

```
# return Depth First Search of tree in list
dfs = obj.get_dfs()  
print(dfs)
```

**输出:**

```
[23, 10, 20, 30, 40]
```

*   **left_view():** 此函数返回树的左视图。

## 蟒蛇 3

```
# return Left View Of Tree in list
left = obj.left_view()
print(left)
```

**输出:**

```
[23, 10, 20]
```

*   **right_view() :** 该函数返回树的右视图。

## 蟒蛇 3

```
# return Right View Of Tree in list
right = obj.right_view()  
print(right)
```

**输出:**

```
[23, 30, 40]
```

*   **total_nodes() :** 此函数返回树中的节点数。

## 蟒蛇 3

```
# return the number of nodes present in the Tree
count = obj.total_nodes() 
print(count)
```

**输出:**

```
5
```