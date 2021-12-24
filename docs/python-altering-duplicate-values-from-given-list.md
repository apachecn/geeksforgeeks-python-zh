# Python |修改给定列表中的重复值

> 原文:[https://www . geeksforgeeks . org/python-修改-复制-给定列表中的值/](https://www.geeksforgeeks.org/python-altering-duplicate-values-from-given-list/)

很多时候，我们处理具有相同数字的列表作为一个序列，我们希望只保留元素的第一次出现，并用不同的数字替换所有出现。让我们讨论一下实现这一点的某些方法。

**方法一:使用列表理解+ `enumerate()`**

这个任务可以使用遍历的列表理解和元素出现的检查来完成，索引检查可以使用枚举函数来完成。

```
# Python3 code to demonstrate
# Altering duplicated
# using list comprehension + enumerate()

# initializing list
test_list = [2, 2, 3, 3, 3, 3, 4, 4, 5, 5, 5]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + enumerate()
# Altering duplicated
res = [False if (ele in test_list[ :idx]) else ele 
             for idx, ele in enumerate(test_list)]

# print result
print("The altered duplicate list is : " + str(res))
```

**Output :**

> 原始列表:[2，2，3，3，3，3，3，4，4，5，5，5]
> 更改后的重复列表为:[2，False，3，False，False，False，4，False，5，False，False]

**方法二:使用`itertools.groupby()` +列表理解**

这个特殊的任务也可以使用上述功能的组合来执行，使用`groupby`功能来获得不同元素的组，并列出理解来更改副本。

```
# Python3 code to demonstrate
# Altering duplicated
# using itertools.groupby() + list comprehension
from itertools import groupby

# initializing list
test_list = [2, 2, 3, 3, 3, 3, 4, 4, 5, 5, 5]

# printing original list
print("The original list : " + str(test_list))

# using itertools.groupby() + list comprehension
# Altering duplicated
res = [val for key, grp in groupby(test_list) 
       for val in [key] + [False] * (len(list(grp))-1)]

# print result
print("The altered duplicate list is : " + str(res))
```

**Output :**

> 原始列表:[2，2，3，3，3，3，3，4，4，5，5，5]
> 更改后的重复列表为:[2，False，3，False，False，False，4，False，5，False，False]