# Python |检查列表中的所有元素是否相同

> 原文:[https://www . geesforgeks . org/python-检查列表中的所有元素是否相同/](https://www.geeksforgeeks.org/python-check-if-all-elements-in-a-list-are-identical/)

给定一个列表，编写一个 Python 程序来检查该列表中的所有元素是否相同。

**示例:**

```
Input : ['a', 'b', 'c']
Output : False

Input : [1, 1, 1, 1]
Output : True

```

**方法#1 :** 使用循环
开始一个 for 循环，并检查第一个元素是否与列表中的所有其他元素相同。这种方法需要 O(n)个时间复杂度。

```
# Python3 program to check if 
# all elements in a list are identical
def check(list):
    return all(i == list[0] for i in list)

# Driver code
print(check(['a', 'b', 'c']))
print(check([1, 1, 1]))
```

**Output:**

```
False
True

```

**方法#2 :** 使用集合
将给定列表转换为集合会移除所有重复的元素，如果结果集大小小于或等于 1，则列表包含所有相同的元素。

```
# Python3 program to check if 
# all elements in a list are identical
def check(list):
   return len(set(list)) <= 1

# Driver code
print(check(['a', 'b', 'c']))
print(check([1, 1, 1]))
```

**Output:**

```
False
True

```

**方法#3 :** 使用`count()`
通过统计列表中第一个元素出现的次数，我们可以检查这个计数是否等于列表的大小。简单地说，检查第一个元素是否在整个列表中重复。

```
# Python3 program to check if 
# all elements in a list are identical
def check(list):
   return list.count(list[0]) == len(list)

# Driver code
print(check(['a', 'b', 'c']))
print(check([1, 1, 1]))
```

**Output:**

```
False
True

```

**方法#4 :** 替代方法
另一种方法是取第一个元素，乘以给定列表的长度，形成一个新列表，使新列表包含与给定列表大小的第一个元素相同的元素，然后与给定列表进行比较。

```
# Python3 program to check if 
# all elements in a list are identical
def check(x):
    return x and [x[0]]*len(x) == x

# Driver code
print(check(['a', 'b', 'c']))
print(check([1, 1, 1]))
```

**Output:**

```
False
True

```

**方法#5 :** 使用扩展切片
Python 切片符号用于检索值的子集。因此，我们将列表的开始到结束与列表的结束到开始进行比较。

```
# Python3 program to check if 
# all elements in a list are identical
def check(list):
   return list[1:] == list[:-1]

# Driver code
print(check(['a', 'b', 'c']))
print(check([1, 1, 1]))
```

**Output:**

```
False
True

```