# Python |将字符串追加到列表中

> 原文:[https://www.geeksforgeeks.org/python-append-string-to-list/](https://www.geeksforgeeks.org/python-append-string-to-list/)

有时，在处理数据时，我们可能会遇到一个问题，需要向容器中添加元素。列表可以包含任何类型的数据类型。让我们讨论在整数列表中执行字符串追加操作的某些方法。

**方法#1:使用+运算符+列表转换**
在该方法中，我们首先将字符串转换为列表，然后使用+运算符执行追加任务。

```py
# Python3 code to demonstrate working of
# Appending String to list
# using + operator + list conversion

# initialize list 
test_list = [1, 3, 4, 5]

# initialize string 
test_str = 'gfg'

# printing original list 
print("The original list : " + str(test_list))

# printing original string 
print("The original string : " + str(test_str))

# Appending String to list
# using + operator + list conversion
test_list += [test_str]

# printing result
print("The list after appending is : " + str(test_list))
```

**Output :**

```py
The original list : [1, 3, 4, 5]
The original string : gfg
The list after appending is : [1, 3, 4, 5, 'gfg']

```