# Python |将给定列表转换为嵌套列表

> 原文:[https://www . geesforgeks . org/python-convert-给定列表-进入嵌套列表/](https://www.geeksforgeeks.org/python-convert-given-list-into-nested-list/)

有时，我们会遇到列表中字符串格式的数据，需要将其转换为列表的列表。这种将字符串列表转换成嵌套列表的问题在 web 开发中非常常见。让我们讨论一下实现这一点的某些方法。

**方法#1:使用迭代**

```py
# Python code to convert list 
# of string into list of list

# List initialization
Input = ['Geeeks, Forgeeks', '65.7492, 62.5405',
         'Geeks, 123', '555.7492, 152.5406']

temp = []

# Getting elem in list of list format
for elem in Input:
    temp2 = elem.split(', ')
    temp.append((temp2))

# List initialization
Output = [] 

# Using Iteration to convert 
# element into list of list
for elem in temp:
    temp3 = []
    for elem2 in elem:
        temp3.append(elem2)
    Output.append(temp3)

# printing
print(Output)
```

**输出:**

> ['Geeks '，' Forgeeks']，['65.7492 '，' 62.5405']，[' Geeks '，' 123']，['555.7492 '，' 152.5406']]