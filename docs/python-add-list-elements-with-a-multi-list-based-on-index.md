# Python |添加基于索引的多列表列表元素

> 原文:[https://www . geesforgeks . org/python-add-list-elements-with-a-multi-list-based-on-index/](https://www.geeksforgeeks.org/python-add-list-elements-with-a-multi-list-based-on-index/)

给定两个列表，一个是简单列表，第二个是多列表，任务是根据索引添加两个列表。

**示例:**

```
Input:
List = [1, 2, 3, 4, 5, 6]
List of list = [[0], [0, 1, 2], [0, 1], [0, 1], [0, 1, 2], [0]]

Output:
[[1], [2, 3, 4], [3, 4], [4, 5], [5, 6, 7], [6]]

Explanation:
[1] = [1+0]
[2, 3, 4] = [0+2, 1+2, 2+2]
[3, 4] = [3+0, 3+1]
[4, 5] = [4+0, 4+1]
[5, 6, 7] = [5+0, 5+1, 5+2]
[6] = [6+0]

```

让我们讨论一些做这个任务的方法。

**方法#1:使用迭代**

```
# Python code to add list elements 
# with a multi-list based on index 

# List initialization
List = [1, 2, 3, 4, 5, 6]
List_of_List = [[0], [0, 1, 2], [0, 1],
                [0, 1], [0, 1, 2], [0]]
Output = []

# Iteration 
for x in range(len(List)):
    temp = []
    for y in List_of_List[x]:
        temp.append(y + List[x])
    Output.append(temp)

# Printing
print("Initial list is:", List)
print("Initial list of list is :", List_of_List)
print("Output is", Output)
```

**Output:**

```
Initial list is: [1, 2, 3, 4, 5, 6]
Initial list of list is : [[0], [0, 1, 2], [0, 1], [0, 1], [0, 1, 2], [0]]
Output is [[1], [2, 3, 4], [3, 4], [4, 5], [5, 6, 7], [6]]

```

**方法 2:使用 enumerate()**

```
# Python code to add list elements 
# with a multi-list based on index

# List initialization
List = [1, 2, 3, 4, 5, 6]
List_of_List = [[0], [0, 1, 2], [0, 1], [0, 1], [0, 1, 2], [0]]
Output = []

# using enumerate 
Output = [[elem + List[x] for elem in y] 
          for x, y in enumerate(List_of_List)]

# Printing
print("Initial list is:", List)
print("Initial list of list is :", List_of_List)
print("Output is", Output)
```

**Output:**

```
Initial list is: [1, 2, 3, 4, 5, 6]
Initial list of list is : [[0], [0, 1, 2], [0, 1], [0, 1], [0, 1, 2], [0]]
Output is [[1], [2, 3, 4], [3, 4], [4, 5], [5, 6, 7], [6]]

```

**方法三:使用`Zip()`**

```
# Python code to add list elements 
# with a multi-list based on index

# List initialization
List = [1, 2, 3, 4, 5, 6]
List_of_List = [[0], [0, 1, 2], [0, 1], [0, 1], [0, 1, 2], [0]]
Output = []

# using zip 
Output = [[z + x for z in y ]for x, y in
                 zip(List, List_of_List)]

# Printing
print("Initial list is:", List)
print("Initial list of list is :", List_of_List)
print("Output is", Output)
```

**Output:**

```
Initial list is: [1, 2, 3, 4, 5, 6]
Initial list of list is : [[0], [0, 1, 2], [0, 1], [0, 1], [0, 1, 2], [0]]
Output is [[1], [2, 3, 4], [3, 4], [4, 5], [5, 6, 7], [6]]

```