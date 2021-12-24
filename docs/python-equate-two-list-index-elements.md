# Python |将两个列表索引元素等同起来

> 原文:[https://www . geesforgeks . org/python-equal-two-list-index-elements/](https://www.geeksforgeeks.org/python-equate-two-list-index-elements/)

有时我们需要从两个列表的索引元素的角度来链接它们，这种问题主要出现在我们需要以格式化的形式显示两个列表之间的链接的地方。这是一个非常具体的问题，但在我们需要一个可能的解决方案时，它可能是有用的。让我们讨论一下实现这一点的某些方法。

**方法#1:使用格式+ `tuple()`**
字符串格式可以用来指定我们需要输出列表的方式，相似索引的配对任务可以借助元组函数来完成。

```
# Python3 code to demonstrate
# Equate two list index elements
# using formatting + tuple()

# initializing lists 
test_list1 = ['GeeksforGeeks', 'is', 'best']
test_list2 = ['1', '2', '3']

# printing original lists 
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# using formatting + tuple() to
# Equate two list index elements
temp = len(test_list1) * '% s = %% s, '
res = temp % tuple(test_list1) % tuple(test_list2)

# printing result
print ("The paired elements string is : " + res)
```

**Output :**

```
The original list 1 is : ['GeeksforGeeks', 'is', 'best']
The original list 2 is : ['1', '2', '3']
The paired elements string is : GeeksforGeeks = 1, is = 2, best = 3, 

```