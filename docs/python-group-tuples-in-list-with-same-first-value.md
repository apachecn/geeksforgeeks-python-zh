# Python |将列表中的元组分组为相同的第一个值

> 原文:[https://www . geesforgeks . org/python-group-tuples-in-list-同值优先/](https://www.geeksforgeeks.org/python-group-tuples-in-list-with-same-first-value/)

给定元组列表，任务是打印另一个包含相同第一元素元组的列表。以下是实现上述任务的一些方法。

**示例:**

```
Input : [('x', 'y'), ('x', 'z'), ('w', 't')]

Output: [('w', 't'), ('x', 'y', 'z')]

```

**方法#1:使用`extend`**

```
# Python code to find common 
# first element in list of tuple

# Function to solve the task
def find(Input):
    out = {}
    for elem in Input:
        try:
            out[elem[0]].extend(elem[1:])
        except KeyError:
            out[elem[0]] = list(elem)
    return [tuple(values) for values in out.values()]

# List initialization
Input = [('x', 'y'), ('x', 'z'), ('w', 't')]

# Calling function
Output = (find(Input))

# Printing
print("Initial list of tuple is :", Input)
print("List showing common first element", Output)
```

**Output:**

```
Initial list of tuple is : [('x', 'y'), ('x', 'z'), ('w', 't')]
List showing common first element [('w', 't'), ('x', 'y', 'z')]

```

**方法 2:使用`defaultdict`**

```
# Python code to find common first
# element in list of tuple

# Importing
from collections import defaultdict

# Function to solve the task
def find(pairs):
    mapp = defaultdict(list)
    for x, y in pairs:
        mapp[x].append(y)
    return [(x, *y) for x, y in mapp.items()]

# Input list initialization
Input = [('p', 'q'), ('p', 'r'),
         ('p', 's'), ('m', 't')]

# calling function
Output = find(Input)

# Printing
print("Initial list of tuple is :", Input)
print("List showing common first element", Output)
```

**Output:**

```
Initial list of tuple is : [('p', 'q'), ('p', 'r'), ('p', 's'), ('m', 't')]
List showing common first element [('m', 't'), ('p', 'q', 'r', 's')]

```