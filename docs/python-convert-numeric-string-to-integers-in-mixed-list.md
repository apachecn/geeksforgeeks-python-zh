# Python |将混合列表中的数字字符串转换为整数

> 原文:[https://www . geesforgeks . org/python-convert-numeric-string-to-integer-in-mixed-list/](https://www.geeksforgeeks.org/python-convert-numeric-string-to-integers-in-mixed-list/)

有时，在处理数据时，我们可能会遇到一个问题，即我们接收混合数据，需要将字符串形式的整数元素转换为整数。在数据预处理步骤中可能需要这种操作。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ isdigit()**
这是执行这个任务的一种方式。在这种情况下，我们使用 isdigit 检查字符串的每个元素是否是数字，如果是数字，则转换为 int。迭代使用列表理解。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert String numbers to integers in mixed List
# using list comprehension + isdigit()

# initialize list
test_list = ["gfg", "1", "is", "6", "best"]

# printing original list
print("The original list : " + str(test_list))

# Convert String numbers to integers in mixed List
# using list comprehension + isdigit()
res = [int(ele) if ele.isdigit() else ele for ele in test_list]

# printing result
print("List after converting string numbers to integers : " + str(res))
```

**Output : **

```
The original list : ['gfg', '1', 'is', '6', 'best']
List after converting string numbers to integers : ['gfg', 1, 'is', 6, 'best']
```

**方法 2:使用 map() + lambda + isdigit()**
这个任务也可以使用上面的函数来执行。在本文中，我们使用 map()和 lambda 函数执行迭代任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert String numbers to integers in mixed List
# using map() + lambda + isdigit()

# initialize list
test_list = ["gfg", "1", "is", "6", "best"]

# printing original list
print("The original list : " + str(test_list))

# Convert String numbers to integers in mixed List
# using map() + lambda + isdigit()
res = list(map(lambda ele : int(ele) if ele.isdigit()
          else ele, test_list))

# printing result
print("List after converting string numbers to integers : " + str(res))
```

**Output : **

```
The original list : ['gfg', '1', 'is', '6', 'best']
List after converting string numbers to integers : ['gfg', 1, 'is', 6, 'best']
```