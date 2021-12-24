# Python |通过在第一个列表

中维护重复项来合并两个列表

> 原文:[https://www . geeksforgeeks . org/python-通过维护来组合两个列表-在第一个列表中重复/](https://www.geeksforgeeks.org/python-combine-two-lists-by-maintaining-duplicates-in-first-list/)

给定两个列表，任务是合并两个列表并删除重复项，而不删除原始列表中的重复项。

**示例:**

```py
Input : 
list_1 = [11, 22, 22, 15]
list_2 = [22, 15, 77, 9]
 Output :
OutList = [11, 22, 22, 15, 77, 9]
```

**代码#1:使用扩展**

```py
# Python code to combine two lists
# and removing duplicates, without
# removing duplicates in original list.

# Initialisation of first list
list1 = [111, 222, 222, 115]

# Initialisation of Second list
list2 = [222, 115, 77, 19]

output = list(list1)

# Using extend function
output.extend(y for y in list2 if y not in output)

# printing result
print(output)
```

****Output:**

```py
[111, 222, 222, 115, 77, 19]

```** 

 ****代码#2:使用集合和迭代**
追加第一个列表中不在第二个列表中的元素，然后取第一个和第二个列表的并集。**

```py
# Python code to combine two lists 
# and removing duplicates, without 
# removing duplicates in original list.

# Initialisation of first list
list1 = [11, 22, 22, 15]

# Initialisation of Second list
list2 = [22, 15, 77, 9]

# creating set
unique_list1 = set(list1)
unique_list2 = set(list2)

# Difference in two sets
diff_element = unique_list2 - unique_list1

# union of difference + first list
output = list1 + list(diff_element)

# printing output
print(output) 
```

****Output:**

```py
[11, 22, 22, 15, 9, 77]

```**