# Python 中列表 VS 集合 VS 元组的区别

> 原文:[https://www . geesforgeks . org/python 中列表 vs 集合 vs 元组的区别/](https://www.geeksforgeeks.org/difference-between-list-vs-set-vs-tuple-in-python/)

[**List:**](https://www.geeksforgeeks.org/python-list/)List**就像动态大小的数组，用其他语言声明(C++中的 vector 和 Java 中的 ArrayList)。列表不需要总是同质的，这使得它成为 [Python](https://www.geeksforgeeks.org/python-programming-language/) 中最强大的工具。列表的主要特征是–**

*   **该列表是 Python 中可用的数据类型，可以写成方括号之间的逗号分隔值(项目)列表。**
*   **列表是可变的，也就是说，它可以转换成另一种数据类型，并且可以在其中存储任何数据元素。**
*   **列表可以存储任何类型的元素。**

****示例:****

## **蟒蛇 3**

```py
# Python3 program to demonstrate 
# List 

# Creating a List
List = []
print("Blank List: ")
print(List)

# Creating a List of numbers
List = [10, 20, 14]
print("\nList of numbers: ")
print(List)

# Creating a List of strings and accessing
# using index
List = ["Geeks", "For", "Geeks"]
print("\nList Items: ")
print(List[0]) 
print(List[2])
```

****输出:****

```py
Blank List: 
[]

List of numbers: 
[10, 20, 14]

List Items: 
Geeks
Geeks
```

**[**元组:**](https://www.geeksforgeeks.org/python-tuples/) 元组是 Python 对象的集合，很像一个列表。存储在元组中的值序列可以是任何类型，并且它们由整数索引。元组的值在语法上用“逗号”分隔。虽然这不是必需的，但是通过在括号中结束值序列来定义元组更常见。元组的主要特征是–**

*   **Tuple 是 python 中的一个不可变序列。**
*   **它不能被改变或替换，因为它是不可变的。**
*   **它在括号()中定义。**
*   **元组可以存储任何类型的元素。**

****示例:****

## **蟒蛇 3**

```py
# Creating an empty Tuple
Tuple1 = ()
print("Initial empty Tuple: ")
print (Tuple1)

# Creating a Tuple with
# the use of list
list1 = [1, 2, 4, 5, 6]
print("\nTuple using List: ")
print(tuple(list1))

#Creating a Tuple 
#with the use of built-in function
Tuple1 = tuple('Geeks')
print("\nTuple with the use of function: ")
print(Tuple1)
```

****输出:****

```py
Initial empty Tuple: 
()

Tuple using List: 
(1, 2, 4, 5, 6)

Tuple with the use of function: 
('G', 'e', 'e', 'k', 's')
```

**[**Set:**](https://www.geeksforgeeks.org/sets-in-python/) 在 Python 中，Set 是一个无序的数据类型集合，它是可迭代的、可变的，并且没有重复的元素。与列表相比，使用集合的主要优点是，它有一个高度优化的方法来检查集合中是否包含特定元素。set 的主要特征是–**

*   **在 python 中，集合是元素的无序集合或项目的意外集合。**
*   **这里元素被添加到集合中的顺序不是固定的，它可以频繁地改变。**
*   **它是在花括号{}下定义的**
*   **集合是可变的，但是，只有不可变的对象可以存储在其中。**

****示例:****

## **蟒蛇 3**

```py
# Python3 program to demonstrate 
# Set in Python

# Creating a Set
set1 = set()
print("Initial blank Set: ")
print(set1)

# Creating a Set with
# the use of Constructor
# (Using object to Store String)
String = 'GeeksForGeeks'
set1 = set(String)
print("\nSet with the use of an Object: " )
print(set1)

# Creating a Set with
# the use of a List
set1 = set(["Geeks", "For", "Geeks"])
print("\nSet with the use of List: ")
print(set1)
```

****输出:****

```py
Initial blank Set: 
set()

Set with the use of an Object: 
{'G', 's', 'e', 'o', 'r', 'F', 'k'}

Set with the use of List: 
{'Geeks', 'For'}
```

### **列表、集合和元组之间的差异表**

<figure class="table">

| 目录 | 一组 | 元组 |
| --- | --- | --- |
| 列表是可变的 | 集合是可变的 | 元组是不可变的 |
| 它是有序的项目集合 | 它是无序的项目集合 | 它是有序的项目集合 |
| 列表中的项目可以替换或更改 | 不能更改或替换集合中的项目 | 元组中的项目不能更改或替换 |

</figure>