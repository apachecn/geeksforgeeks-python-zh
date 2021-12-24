# Python 中的 cmp(列表)方法

> 原文:[https://www . geesforgeks . org/python-2-number-cmplist-method/](https://www.geeksforgeeks.org/python-2-number-cmplist-method/)

cmp(list)是 Python 2 中的 Number 中指定的方法。

已经使用 [cmp()](https://www.geeksforgeeks.org/python-cmp-function/) 讨论了整数的比较。但是很多时候，需要比较由相似或不同数据类型组成的整个列表。在这种情况下，会出现不同的案例场景，了解它们有时会非常方便。

该函数将 2 个列表作为输入，检查第一个参数列表是否大于、等于或小于第二个参数列表。

> 语法: **cmp(列表 1，列表 2)**
> 
> **参数:**
> **列表 1 :** 要比较的第一个参数列表。
> **列表 2 :** 要比较的第二个参数列表。
> 
> **返回:**如果第一个列表“大于”第二个列表，则该函数返回 1，如果第一个列表小于第二个列表，则返回-1，否则如果两个列表相等，则返回 0。

在某些情况下，我们需要决定一个列表是更小、更大还是等于另一个列表。

**情况 1 :** 当列表只包含整数时。

当列表中的所有元素都是整数类型时就是这种情况，因此当进行比较时，从左到右进行逐个数字的比较，如果我们在任何特定索引处得到一个更大的数字，我们称之为更大，并停止进一步的比较。如果两个列表中的所有元素都相似，并且一个列表比另一个列表大(在大小上)，则认为较大的列表更大。

**代码#1 :** 仅使用整数演示 cmp()。

```
# Python code to demonstrate 
# the working of cmp()
# only integer case.

# initializing argument lists
list1 = [ 1, 2, 4, 3]
list2 = [ 1, 2, 5, 8]
list3 = [ 1, 2, 5, 8, 10]
list4 = [ 1, 2, 4, 3]

# Comparing lists 
print "Comparison of list2 with list1 : ",
print cmp(list2, list1)

# prints -1, because list3 has larger size than list2
print "Comparison of list2 with list3(larger size) : ",
print cmp(list2, list3)

# prints 0 as list1 and list4 are equal
print "Comparison of list4 with list1(equal) : ",
print cmp(list4, list1)
```

输出:

```
Comparison of list2 with list1 :  1
Comparison of list2 with list3(larger size) :  -1
Comparison of list4 with list1(equal) :  0

```

**情况 2 :** 当列表包含多个数据类型时。
当一个以上的数据类型，如字符串包含在字符串中时，字符串被认为大于整数，这样，所有的数据类型都按字母顺序排序，以备比较。在这种情况下，大小规则保持不变。

**代码#2 :** 演示使用多种数据类型的 cmp()。

```
# Python code to demonstrate 
# the working of cmp()
# multiple data types

# initializing argument lists
list1 = [ 1, 2, 4, 10]
list2 = [ 1, 2, 4, 'a']
list3 = [ 'a', 'b', 'c']
list4 = [ 'a', 'c', 'b']

# Comparing lists 
# prints 1 because string
# at end compared to number
# string is greater
print "Comparison of list2 with list1 : ",
print cmp(list2, list1)

# prints -1, because list3
# has an alphabet at beginning
# even though size of list2
# is greater, Comparison
# is terminated at 1st
# element itself.
print "Comparison of list2 with list3(larger size) : ",
print cmp(list2, list3)

# prints -1 as list4 is greater than
# list3
print "Comparison of list3 with list4 : ",
print cmp(list3, list4)
```

输出:

```
Comparison of list2 with list1 :  1
Comparison of list2 with list3(larger size) :  -1
Comparison of list3 with list4 :  -1

```