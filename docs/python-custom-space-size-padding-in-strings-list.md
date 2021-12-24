# Python–字符串列表中的自定义空间大小填充

> 原文:[https://www . geesforgeks . org/python-custom-space-size-strings-padding-list/](https://www.geeksforgeeks.org/python-custom-space-size-padding-in-strings-list/)

在本文中，给定一个字符串列表，任务是编写一个 Python 程序，用空格填充每个字符串，并指定所需的前导和尾随空格数。

**示例:**

> **输入:**test _ list =[“Gfg”、“is”、“Best”]，lead_size = 3，trail_size = 2
> 
> **输出:** [' Gfg '，' is '，' Best ']
> 
> **说明:**每个单词 3 个空格后开始，完成后加 2 个空格。
> 
> **输入:**test _ list =[“Gfg”、“Best”]，lead_size = 3，trail_size = 2
> 
> **输出:** [' Gfg '，' Best ']
> 
> **说明:**每个单词 3 个空格后开始，完成后加 2 个空格。

**方法#1:使用循环**

在本文中，我们使用循环执行添加尾随和前导所需空格的任务。*运算符用于获取所需的空格数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Custom space size padding in Strings List
# Using loop

# initializing lists
test_list = ["Gfg", "is", "Best"]

# printing original list
print("The original list is : " + str(test_list))

# initializing padding numbers
lead_size = 3
trail_size = 2

res = []
for ele in test_list:

    # * operator handles number of spaces
    res.append((lead_size * ' ') + ele + (trail_size * ' '))

# printing result
print("Padded Strings : " + str(res))
```

**输出:**

```
The original list is : ['Gfg', 'is', 'Best']
Padded Strings : ['   Gfg  ', '   is  ', '   Best  ']
```

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

类似于上面的方法，唯一的区别是使用列表理解作为解决问题的单行替代方法。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Custom space size padding in Strings List
# Using list comprehension

# initializing lists
test_list = ["Gfg", "is", "Best"]

# printing original list
print("The original list is : " + str(test_list))

# initializing padding numbers
lead_size = 3
trail_size = 2

# using list comprehension for one liner alternative
res = [(lead_size * ' ') + ele + (trail_size * ' ') for ele in test_list]

# printing result
print("Padded Strings : " + str(res))
```

**输出:**

```
The original list is : ['Gfg', 'is', 'Best']
Padded Strings : ['   Gfg  ', '   is  ', '   Best  ']
```