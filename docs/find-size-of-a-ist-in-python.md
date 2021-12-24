# 在 Python 中找到列表的大小

> 原文:[https://www.geeksforgeeks.org/find-size-of-a-ist-in-python/](https://www.geeksforgeeks.org/find-size-of-a-ist-in-python/)

在 [Python 中](https://www.geeksforgeeks.org/python-programming-language/)、 [List](https://www.geeksforgeeks.org/list-cpp-stl/) 是一个有序可变的集合数据类型。列表也可以有重复条目。这里的任务是找出列表中条目的数量。请看下面的例子。

示例:

```py
Input : a = [1, 2, 3, 1, 2, 3]
Output : 6
Count the number of entries in the list a.

Input : a = []
Output : 0

```

想法是在 Python 中使用 [len()](https://www.geeksforgeeks.org/list-methods-in-python-set-1-in-not-in-len-min-max/)

```py
# Python program to demonstrate working
# of len()
a = []
a.append("Hello")
a.append("Geeks")
a.append("For")
a.append("Geeks")
print("The length of list is: ", len(a))
```

**Output:**

```py
The length of list is:  4

```

例 2:

```py
# Python program to demonstrate working
# of len()
n = len([10, 20, 30])
print("The length of list is: ", n)
```

**Output:**

```py
The length of list is:  3

```

**len()是如何工作的？**
len()在 O(1)时间工作，因为 list 是一个对象，并且有一个成员来存储它的大小。以下是 [Python 文档](https://docs.python.org/3/library/functions.html#len)中对 len()的描述。

> 返回对象的长度(项目数)。参数可以是序列(如字符串、字节、元组、列表或范围)或集合(如字典、集合或冻结集合)。

**[如何在 Python 中检查列表是否为空](https://www.geeksforgeeks.org/python-check-whether-list-empty-not/)**