# Python |从列表中获取唯一值

> 原文:[https://www . geesforgeks . org/python-get-unique-values-list/](https://www.geeksforgeeks.org/python-get-unique-values-list/)

给定一个列表，以任何顺序打印所有唯一的数字。
**例:**

```
Input : 10 20 10 30 40 40
Output : 10 20 30 40 

Input : 1 2 1 1 3 4 3 3 5 
Output : 1 2 3 4 5  
```

**方法 1:遍历列表**

使用遍历，我们可以遍历列表中的每个元素，并检查该元素是否已经在 unique_list 中如果它不在那里，那么我们可以将它追加到 unique_list 中。这是使用一个 for 循环和另一个 if 语句来完成的，这两个语句检查值是否在唯一列表中，这相当于另一个 for 循环。

## 计算机编程语言

```
# Python program to check if two
# to get unique values from list
# using traversal

# function to get unique values
def unique(list1):

    # initialize a null list
    unique_list = []

    # traverse for all elements
    for x in list1:
        # check if exists in unique_list or not
        if x not in unique_list:
            unique_list.append(x)
    # print list
    for x in unique_list:
        print x,

# driver code
list1 = [10, 20, 10, 30, 40, 40]
print("the unique values from 1st list is")
unique(list1)

list2 =[1, 2, 1, 1, 3, 4, 3, 3, 5]
print("\nthe unique values from 2nd list is")
unique(list2)
```

**输出:**

```
the unique values from 1st list is
10 20 30 40 
the unique values from 2nd list is
1 2 3 4 5
```

**方法二:使用套装**

使用 Python 的 [set()](https://www.geeksforgeeks.org/sets-in-python/) 属性，我们可以轻松检查唯一值。在集合中插入列表的值。Set 只存储一次值，即使该值被多次插入。将 set by list_set=set(list1)中的所有值插入后，将该集合转换为列表以进行打印。

## 计算机编程语言

```
# Python program to check if two
# to get unique values from list
# using set

# function to get unique values
def unique(list1):

    # insert the list to the set
    list_set = set(list1)
    # convert the set to the list
    unique_list = (list(list_set))
    for x in unique_list:
        print x,

# driver code
list1 = [10, 20, 10, 30, 40, 40]
print("the unique values from 1st list is")
unique(list1)

list2 =[1, 2, 1, 1, 3, 4, 3, 3, 5]
print("\nthe unique values from 2nd list is")
unique(list2)
```

**输出:**

```
the unique values from 1st list is
40 10 20 30 
the unique values from 2nd list is
1 2 3 4 5
```

**方法三:使用 numpy.unique**

使用 Python 的导入 numpy，还可以获得数组中唯一的元素。第一步，将列表转换为 **x=numpy.array(列表)**，然后使用 **numpy.unique(x)** 函数从列表中获取唯一值。 **numpy.unique()** 只返回列表中的唯一值。

## 蟒蛇 3

```
#Ppython program to check if two
# to get unique values from list
# using numpy.unique
import numpy as np

# function to get unique values
def unique(list1):
    x = np.array(list1)
    print(np.unique(x))

# driver code
list1 = [10, 20, 10, 30, 40, 40]
print("the unique values from 1st list is")
unique(list1)

list2 =[1, 2, 1, 1, 3, 4, 3, 3, 5]
print("\nthe unique values from 2nd list is")
unique(list2)
```

**输出**T2】

```
the unique values from 1st list is
[10 20 30 40]

the unique values from 2nd list is
[1 2 3 4 5]
```

**方法#4:使用集合。计数器()**

使用 python 从集合中导入 Counter()打印 Counter 元素的所有键，或者我们使用**“***符号直接打印。

下面是上述方法的实现。

## 蟒蛇 3

```
# Python program to check if two
# to get unique values from list
# importing counter from collections
from collections import Counter

# Function to get unique values
def unique(list1):

    # Print directly by using * symbol
    print(*Counter(list1))

# driver code
list1 = [10, 20, 10, 30, 40, 40]
print("the unique values from 1st list is")
unique(list1)

list2 = [1, 2, 1, 1, 3, 4, 3, 3, 5]
print("\nthe unique values from 2nd list is")
unique(list2)

# This code is contributed by vikkycirus
```

**输出:**

```
the unique values from 1st list is
10 20 30 40

the unique values from 2nd list is
1 2 3 4 5
```