# Python |如何复制嵌套列表

> 原文:[https://www . geesforgeks . org/python-如何复制嵌套列表/](https://www.geeksforgeeks.org/python-how-to-copy-a-nested-list/)

在上一篇文章中，我们已经看到了如何[克隆或复制一个列表](https://www.geeksforgeeks.org/python-cloning-copying-list/)，现在让我们看看如何在 Python 中复制一个嵌套列表。

**方法#1:使用迭代**

```
# Python program to copy a nested list

# List initialization
Input_list = [[0, 1, 2], [3, 4, 5], ]
Output = [] 

# Using iteration to assign values
for x in range(len(Input_list)):
    temp = []
    for elem in Input_list[x]:
        temp.append(elem)
    Output.append(temp)

# Printing Output
print("Initial list is:")
print(Input_list)
print("New assigned list is")
print(Output)
```

**输出:**

```
Initial list is:
[[0, 1, 2], [3, 4, 5]]
New assigned list is
[[0, 1, 2], [3, 4, 5]]

```