# Python |列表和元组的区别

> 原文:[https://www . geeksforgeeks . org/python-列表和元组的区别/](https://www.geeksforgeeks.org/python-difference-between-list-and-tuple/)

Python 中的 List 和 Tuple 是数据结构的类。列表是动态的，而元组具有静态特征。
[**列表**](https://www.geeksforgeeks.org/python-list/) 就像数组一样，用其他语言声明。列表不必总是同质的，这使得它成为 Python 中最强大的工具。在 Python 中，列表是数据结构中的一种容器，用于同时存储多个数据。列表是保存数据序列并对其进行进一步迭代的有用工具。
**语法:**

```py
list_data = ['an', 'example', 'of', 'a', 'list']
```

[Tuple](https://www.geeksforgeeks.org/tuples-in-python/) 也是一个序列数据类型，可以包含不同数据类型的元素，但这些本质上是不可变的。换句话说，元组是由逗号分隔的 Python 对象的集合。元组比列表快，因为本质上是静态的。
**语法:**

```py
tuple_data = ('this', 'is', 'an', 'example', 'of', 'tuple')
```

**Python 中列表和元组的区别:**

<figure class="table">

| 不，先生。 | 目录 | 元组 |
| --- | --- | --- |
| one | 列表是可变的 | 元组是不可变的 |
| Two | 迭代的含义是耗时的 | 迭代的含义相对更快 |
| three | 该列表更适合执行插入和删除等操作。 | 元组数据类型适合访问元素 |
| four | 列表会消耗更多内存 | 与列表相比，元组消耗更少的内存 |
| five | 列表有几个内置方法 | Tuple 没有很多内置方法。 |
| six | 意外的变化和错误更容易发生 | 在元组中，很难发生。 |

</figure>