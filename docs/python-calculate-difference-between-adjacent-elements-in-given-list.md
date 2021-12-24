# Python |计算给定列表中相邻元素之间的差异

> 原文:[https://www . geesforgeks . org/python-计算给定列表中相邻元素之间的差异/](https://www.geeksforgeeks.org/python-calculate-difference-between-adjacent-elements-in-given-list/)

给定一个列表，任务是创建一个包含给定列表中相邻元素差异的新列表。

**方法一:使用`zip()`**

```py
# Python code to demonstrate
# to calculate difference
# between adjacent elements in list

# initialising _list
ini_list = [5, 4, 89, 12, 32, 45]

# printing iniial_list
print("intial_list", str(ini_list))

# Calculating difference list
diff_list = []
for x, y in zip(ini_list[0::], ini_list[1::]):
    diff_list.append(y-x)

# printing difference list
print ("difference list: ", str(diff_list))

```

**输出:**

```py
intial_list [5, 4, 89, 12, 32, 45]
difference list:  [-1, 85, -77, 20, 13]

```