# 如何统计列表内的唯一值

> 原文:[https://www . geesforgeks . org/如何计数-列表中的唯一值/](https://www.geeksforgeeks.org/how-to-count-unique-values-inside-a-list/)

在 Python 中，有几种方法可以查找或计算列表中的唯一项目。这里我们将讨论 3 种方法。

**方法 1:**

第一种方法是蛮力方法。这种方法效率不高，因为它需要更多的时间和空间。在这个方法中，我们取一个空数组和一个计数变量(设置为零)。我们从头开始遍历并检查项目。如果该项目不在空列表中(因为它已被清空)，那么我们将把它添加到空列表中，并将计数器增加 1。旅行时，如果物品在被拍清单(空清单)中，我们不会计算在内。

**示例:**

## 蟒蛇 3

```py
# taking an input list
input_list = [1, 2, 2, 5, 8, 4, 4, 8]

# taking an input list
l1 = []

# taking an counter
count = 0

# travesing the array
for item in input_list:
    if item not in l1:
        count += 1
        l1.append(item)

# printing the output
print("No of unique items are:", count)
```

**输出:**

```py
No of unique items are: 5

```

**方法二:**

在这个方法中，我们将使用一个函数名 **Counter。**模块**集合**有此功能。使用**计数器**功能，我们将创建一个字典。字典的**键**将是唯一的项目，值将是列表中该键的编号。我们将使用键创建一个列表，列表的长度将是我们的答案。

## 蟒蛇 3

```py
# importing Counter module
from collections import Counter

input_list = [1, 2, 2, 5, 8, 4, 4, 8]

# creating a list with the keys
items = Counter(input_list).keys()
print("No of unique items in the list are:", len(items))
```

**输出:**

```py
No of unique items in the list are: 5

```

如果我们打印使用 Counter 创建的字典的长度，也会给出结果。但是这种方法更容易理解。

**方法 3:**

在这个方法中，我们将把我们的列表转换成集合。由于**集合**不包含任何重复的项目，那么打印集合的长度将给出唯一项目的总数。

## 蟒蛇 3

```py
input_list = [1, 2, 2, 5, 8, 4, 4, 8]

# converting our list to set
new_set = set(input_list)
print("No of unique items in the list are:", len(new_set))
```

**输出:**

```py
No of unique items in the list are: 5

```