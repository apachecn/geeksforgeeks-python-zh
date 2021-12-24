# 高级 Python 列表方法和技术

> 原文:[https://www . geesforgeks . org/advanced-python-list-methods-and-technologies/](https://www.geeksforgeeks.org/advanced-python-list-methods-and-techniques/)

列表就像动态大小的数组，用其他语言声明(C++中的 vector 和 Java 中的 ArrayList)。列表不必总是同质的，这使得它成为 Python 中最强大的工具。单个列表可能包含整数、字符串和对象等数据类型。列表是可变的，因此，即使在创建之后，它们也可以被更改。

列表是 python 中最强大的工具之一。他们有很多隐藏的技巧，这使得他们非常多才多艺。让我们来探索一些让我们的生活变得更轻松的有用的技巧吧！！！

### **整理列表**

要按升序或降序对列表进行排序，我们使用具有以下语法的 [*【排序】)*](https://www.geeksforgeeks.org/sort-in-python/) 函数:

```
For ascending order: 
list.sort()
For descending order: 
list.sort(reverse=True)
```

**示例:**

## 蟒蛇 3

```
# sorting a list using sort() function

my_list = [5, 2, 90, 24, 10]

# sorting in ascending order it permanently
# changes the order of the list
my_list.sort()
print(my_list)

# sorting in descending order it permanently
# changes the order of the list
my_list.sort(reverse=True)
print(my_list)
```

**输出:**

```
[2, 5, 10, 24, 90]
[90, 24, 10, 5, 2]
```

要临时更改列表的顺序，请使用以下语法的 [*【排序】(*](https://www.geeksforgeeks.org/sorted-function-python/) 函数:

```
list.sorted()
```

## 蟒蛇 3

```
# temporary sorting using sorted() method

my_list = [5, 2, 90, 24, 10]

# ascending order
print(sorted(my_list))

# descending order
my_list_2 = sorted(my_list)
print(my_list)
```

**输出:**

```
[2, 5, 10, 24, 90]
[5, 2, 90, 24, 10]
```

### **反转列表**

要反转列表的顺序，我们使用 [*【反转()*](https://www.geeksforgeeks.org/python-reversing-list/) 功能。它的语法是:

```
list.reverse()
```

**示例:**

## 蟒蛇 3

```
# reverse a list using reverse()

my_list = [5, 2, 90, 24, 10]

# reverse
my_list.reverse()
print(my_list)
```

**输出:**

```
[10, 24, 90, 2, 5]
```

或者我们可以应用列表理解来反转列表:

```
 list = list[::-1]
```

**示例:**

## 蟒蛇 3

```
# reverse using list comprehension
my_list = [5, 2, 90, 24, 10]

# reverse
print(my_list[::-1])
```

**输出:**

```
[10, 24, 90, 2, 5]
```

### **删除重复项**

因为 python 中的字典不包含重复的键。我们使用 [*dict.fromkeys()*](https://www.geeksforgeeks.org/python-dictionary-fromkeys-method/) 函数将我们的列表转换为以列表元素为关键字的字典。然后我们把字典转换回列表。

这是一个自动删除所有重复项的强大技巧。它的语法是:

```
My_list =[‘a’, ’b’, ’c’, ’b’, ’a’]
Mylist = list(dict.fromkeys(My_List))
```

**示例:**

## 蟒蛇 3

```
# removing duplicates from a list using dictionaries

my_list_1 = [5, 2, 90, 24, 10, 2, 90, 34]
my_list_2 = ['a', 'a', 'a', 'b', 'c', 'd', 'd', 'e']

# removing duplicates from list 1
my_list_1 = list(dict.fromkeys(my_list_1))
print(my_list_1)

# removing duplicates from list 2
my_list_2 = list(dict.fromkeys(my_list_2))
print(my_list_2)
```

**输出:**

```
[5, 2, 90, 24, 10, 34]
['a', 'b', 'c', 'd', 'e']
```

### 过滤列表

Python 列表可以借助 [*filter()*](https://www.geeksforgeeks.org/filter-in-python/) 功能或者借助列表理解进行过滤。以下是语法:

```
My_list = list(filter(filter_function , iterable_item))
```

Filter 函数返回一个迭代器对象，我们必须将其转换回列表。

**示例:**

## 蟒蛇 3

```
# filtering with the help of filter() function
# creating a filter function filter all the values less than 20

# filter function
def my_filter(n):
    if n > 20:
        return n

# driver code
if __name__ == "__main__":
    my_list = [5, 2, 90, 24, 10, 2, 95, 36]
    my_filtered_list = list(filter(my_filter, my_list))
    print(my_filtered_list)
```

**输出:**

```
[90, 24, 95, 36]
```

我们也可以使用列表理解进行过滤。这是一种更简单、更优雅的过滤列表的方法，下面是语法:

```
My_list = [item for item in my_list if (condition)]
```

**示例:**

## 蟒蛇 3

```
# filtering with the help of list comprehension
my_list = [5, 2, 90, 24, 10, 2, 95, 36]

# an elegant way to sort the list
my_list = [item for item in my_list if item > 20]
print(my_list)
```

**输出:**

```
[90, 24, 95, 36]
```

### 修改列表

为了在外部函数的帮助下修改列表中的值，我们使用了 map()函数。Map()函数将给定函数应用于给定可迭代表(列表、元组等)的每个元素后，返回结果的 map 对象(迭代器)。).以下是语法:

```
My_list = list(map(function,iterable))
```

**示例:**

## 蟒蛇 3

```
# using map() function to modify the text
def squaring(n):
    return n**2

# driver code
if __name__ == "__main__":
    my_list = [5, 2, 90, 24, 10, 2, 95, 36]

    my_squared_list = list(map(squaring, my_list))
    print(my_squared_list)
```

**输出:**

```
[25, 4, 8100, 576, 100, 4, 9025, 1296]
```

一个更干净的方法是使用列表理解。

**示例:**

## 蟒蛇 3

```
# the same result can be obtained by a much pythonic approach
# i.e., by using list comprehension
my_list = [5, 2, 90, 24, 10, 2, 95, 36]

print([i**2 for i in my_list])
```

**输出:**

```
[25, 4, 8100, 576, 100, 4, 9025, 1296]
```

### 组合列表

我们甚至可以借助 [*zip()*](https://www.geeksforgeeks.org/zip-in-python/) 函数将列表组合起来，从而得到一个元组列表。这里，来自列表 A 的每个项目以元组的形式与来自列表 B 的相应元素组合。以下是语法:

```
My_list = zip(list_1, list_2)
```

**示例:**

## 蟒蛇 3

```
# combing lists with the help of zip() function
my_list_1 = [5, 2, 90, 24, 10]
my_list_2 = [6, 3, 91, 25, 12]

# combined
my_combined_list = list(zip(my_list_1, my_list_2))
print(my_combined_list)
```

**输出:**

```
[(5, 6), (2, 3), (90, 91), (24, 25), (10, 12)]
```

### 查找最常见的项目

为了找到最频繁的元素，我们使用 [*set()*](https://www.geeksforgeeks.org/python-set-method/) 功能。 *set()* 函数从列表中删除所有重复的元素，而 [*max()*](https://www.geeksforgeeks.org/python-max-function/) 函数返回最频繁的元素(在‘键’的帮助下找到)。该键是可选的单参数函数。以下是语法:

```
Most_frequent_value =max(set(my_list),key=mylist.count)
```

**示例:**

## 蟒蛇 3

```
# to find the most frequent element from the list
my_list = ['a', 'a', 'a', 'b', 'c', 'd', 'd', 'e']

most_frequent_value = max(set(my_list), key=my_list.count)

print("The most common element is:", most_frequent_value)
```

**输出:**

```
The most common element is: a
```

### 检查列表中的成员资格

为了检查一个项目是否存在于列表中，我们使用语句中的*。*

**示例:**

## 蟒蛇 3

```
my_list = ['a', 'a', 'a', 'b', 'c', 'd', 'd', 'e']

# to check whether 'c' is a member of my_list
# returns true if present
print('c' in my_list) 

# to check whether 'f' is a member of my_list
# returns false if not present
print('f' in my_list)
```

**输出:**

```
True
False
```

### 展平列表列表

有时我们会遇到一个列表，其中每个元素本身就是一个列表。为了把一个列表转换成一个单独的列表，我们使用列表理解。

```
my_list = [item  for List in list_of_lists for item in List ]
```

**示例:**

## 蟒蛇 3

```
# to flatten a list_of_lists by using list comprehension
list_of_lists = [[1, 2],
                 [3, 4],
                 [5, 6],
                 [7, 8]]

# using list comprehension
my_list = [item for List in list_of_lists for item in List]
print(my_list)
```

**输出:**

```
[1, 2, 3, 4, 5, 6, 7, 8]
```