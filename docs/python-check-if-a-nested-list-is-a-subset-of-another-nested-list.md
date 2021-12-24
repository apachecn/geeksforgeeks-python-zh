# Python |检查一个嵌套列表是否是另一个嵌套列表的子集

> 原文:[https://www . geesforgeks . org/python-检查嵌套列表是否是另一个嵌套列表的子集/](https://www.geeksforgeeks.org/python-check-if-a-nested-list-is-a-subset-of-another-nested-list/)

给定两个列表*列表 1* 和*列表 2* ，检查*列表 2* 是否是*列表 1* 的子集，并相应地返回真或假。

**示例:**

```
Input : list1 = [[2, 3, 1], [4, 5], [6, 8]]
        list2 = [[4, 5], [6, 8]]
Output : True

Input : list1 = [['a', 'b'], ['e'], ['c', 'd']]
        list2 = [['g']]
Output : False

```

我们来讨论几个解决问题的方法。

**方法#1:天真的方法**
取一个变量“存在”，它跟踪每个元素，不管它是否出现在列表 1 中。开始一个循环，在每次迭代“I”中，检查列表 1 中是否存在第 i <sup>个</sup>元素。如果存在，将“存在”设置为“真”或“假”。

```
# Python3 Program to Check is a nested 
# list is a subset of another nested list

def checkSubset(list1, list2):
    l1, l2 = list1[0], list2[0]
    exist = True
    for i in list2:
        if i not in list1:
            exist = False
    return exist

# Driver Code
list1 = [[2, 3, 1], [4, 5], [6, 8]]
list2 = [[4, 5], [6, 8]]
print(checkSubset(list1, list2))
```

**Output:**

```
True

```

**方法 2:使用 Python 集合**
将两个给定嵌套列表的每个子列表转换为元组，因为集合不能保存列表，因为它们依赖于它们的元素是不可变的，并且列表是可变的。但是将它们转换成元组效果很好。之后，只需检查 list2 的集合是否是 list1 的子集。

```
# Python3 Program to Check is a nested 
# list is a subset of another nested list

def checkSubset(list1, list2):
    temp1 = []
    temp2 = []
    for i in list1:
        temp1.append(tuple(i))
    for i in list2:
        temp2.append(tuple(i))

    return set(temp2) < set(temp1)

# Driver Code
list1 = [[2, 3, 1], [4, 5], [6, 8]]
list2 = [[4, 5], [6, 8]]
print(checkSubset(list1, list2))
```

**Output:**

```
True

```

**方法 3:使用 *all* 和 for loop**T5】此方法使用 for loop 检查所有元素(使用 *all* )是否属于列表 1。

```
# Python3 Program to Check is a nested 
# list is a subset of another nested list

def checkSubset(list1, list2):
    return all(x in list1 for x in list2)

# Driver Code
list1 = [[2, 3, 1], [4, 5], [6, 8]]
list2 = [[4, 5], [6, 8]]
print(checkSubset(list1, list2))
```

**Output:**

```
True

```

**方法#4:使用`map()`和`__contains__`**
在这种方法中，我们使用 Python `map()`使用“包含检查”运算符 __contains__，检查列表 1 元素是否包含在列表 2 中。

```
# Python3 Program to Check is a nested 
# list is a subset of another nested list

def checkSubset(list1, list2):
    return all(map(list1.__contains__, list2))

# Driver Code
list1 = [[2, 3, 1], [4, 5], [6, 8]]
list2 = [[4, 5], [6, 8]]
print(checkSubset(list1, list2))
```

**Output:**

```
True

```