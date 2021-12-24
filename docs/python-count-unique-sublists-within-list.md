# Python |统计列表中唯一的子列表

> 原文:[https://www . geesforgeks . org/python-count-unique-sublist-in-list/](https://www.geeksforgeeks.org/python-count-unique-sublists-within-list/)

给定一个列表列表，任务是查找列表中唯一子列表的计数。

**示例:**

```
Input: [['Geek', 'for', 'geeks'], ['geeks', 'for'],
        ['for', 'Geeks', 'geek'], ['Geek', 'for', 'geeks']]

Output:
{('geeks', 'for'): 1, ('for', 'Geeks', 'geek'): 1, 
 ('Geek', 'for', 'geeks'): 2}

```

下面是一些完成任务的方法。

**方法#1:使用迭代**

```
# Python code to count unique sublist within list

# Input list initialization
Input = [['Geek', 'for', 'geeks'], ['geeks', 'for'],
         ['for', 'Geeks', 'geek'], ['Geek', 'for', 'geeks']]

# Output list initialization
Output = {}

# Using Iteration
for lis in Input:
    Output.setdefault(tuple(lis), list()).append(1)
for a, b in Output.items():
    Output[a] = sum(b)

# Printing output
print(Output)
```

**Output:**

> {(“极客”，“为”，“极客”):2，(“极客”，“为”):1，(“为”，“极客”，“极客”):1}

**方法 2:使用计数器**

```
# Python code to find count of unique list in list of list

# Importing counter from collection
from collections import Counter

# Input list initialization
lst = [[1, 2, 3], [4, 5, 6], [3, 2, 1], [1, 2, 3]]

# Using counter
Output = Counter([tuple(i) for i in lst])

# Printing output
print(Output)
```

**Output:**

```
Counter({(1, 2, 3): 2, (3, 2, 1): 1, (4, 5, 6): 1})

```

**方法三:利用熊猫**

```
# Python code to count unique sublist within list

# Importing 
from collections import Counter
import pandas as pd                     

# Input list initialization
lst = [[1, 2, 3], [4, 5, 6], [3, 2, 1], [1, 2, 3]]

# Getting count
dict = Counter([tuple(i) for i in lst])

# Creating pandas dataframe
Output = pd.DataFrame(data ={'list': list(dict.keys()),
                         'count': list(dict.values())})

# Printing output
print(Output)
```

**Output:**

```
count       list
0      1  (3, 2, 1)
1      1  (4, 5, 6)
2      2  (1, 2, 3)

```