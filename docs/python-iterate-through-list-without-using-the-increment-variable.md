# Python–不使用增量变量

迭代列表

> 原文:[https://www . geeksforgeeks . org/python-迭代列表-不使用增量变量/](https://www.geeksforgeeks.org/python-iterate-through-list-without-using-the-increment-variable/)

python**[list](https://www.geeksforgeeks.org/python-list/)很像大小灵活的数组，用 C++中的 vector、Java 中的数组 list 等其他语言声明。列表是异构的，这使得它成为 Python 中最有效的特性。列表是可变的，因此即使在形成之后也可以修改。**

**最常见的方法是使用增量变量 *i:* 遍历列表**

## **蟒蛇 3**

```
# Initializing the list
List = ["Geeks", 4, 'Geeks!']

# Using index variable to access
# each element of the list
for i in range(len(List)):
    print(List[i], end=" ")
```

****输出:****

```
Geeks 4 Geeks! 
```

**这是最常见的做法，其中索引变量 *i* 仅使用列表中每个元素的索引来访问该列表的每个元素。但是，有多种方法可以在不使用索引变量的情况下遍历列表。**

**下面是一些不使用索引变量遍历列表的方法:**

****方法 1:****

**使用每个元素的公共变量而不是索引显式地遍历列表。**

## **蟒蛇 3**

```
# Initializing the list
List = ["Geeks", 4, 'Geeks!']

# Using a common variable to access
# each element of the list
for ele in List:
    print(ele, end=" ")
```

****输出:****

```
Geeks 4 Geeks! 
```

****方法二:****

**[*enumerate()*](https://www.geeksforgeeks.org/enumerate-in-python/) 方法在列表中添加一个计数器，并以枚举对象的形式返回，可用于访问列表的元素**

## **蟒蛇 3**

```
# Initializing the list
List = ["Geeks", 4, 'Geeks!']

# Using enumerate()
for ele in enumerate(List):
    print(ele[1], end=" ")
```

****输出:****

```
Geeks 4 Geeks! 
```

****方法 3:****

**使用 [*numpy*](https://www.geeksforgeeks.org/python-numpy/) 中的 [*nditer()*](https://www.geeksforgeeks.org/numpy-iterating-over-array/) 方法，在将列表转换为数组后对其进行迭代。**

## **蟒蛇 3**

```
# Importing required modules
import numpy

# Initializing the list
List = ["Geeks", 4, 'Geeks!']

# Converting to array
Array = numpy.array(List)

# Using enumerate
for ele in numpy.nditer(Array):
    print(ele, end=" ")
```

****输出:****

```
Geeks 4 Geeks!
```