# Python |从给定的列表列表中获取正元素

> 原文:[https://www . geeksforgeeks . org/python-从给定列表中获取正元素/](https://www.geeksforgeeks.org/python-get-positive-elements-from-given-list-of-lists/)

给定一个列表，任务是从给定的列表中只获取正元素。以下是解决上述问题的一些方法。

**方法#1:使用迭代**

```
# Python code to get positive 
# element from list of list

# List Initialisation
Input = [[10, -11, 222], [42, -222, -412, 99, -87]]
Output = []

# Using iteration
for elem in Input:
    temp = []
    for x in elem:
        if x>0:
            temp.append(x)
    Output.append(temp)

# printing output
print("Initial List is :", Input)
print("Modified list is :", Output)
```

**输出:**

```
Initial List is : [[10, -11, 222], [42, -222, -412, 99, -87]]
Modified list is : [[10, 222], [42, 99]]

```