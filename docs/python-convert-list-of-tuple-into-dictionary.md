# Python |将元组列表转换为字典

> 原文:[https://www . geesforgeks . org/python-convert-list-of-tuple-to-dictionary/](https://www.geeksforgeeks.org/python-convert-list-of-tuple-into-dictionary/)

给定一个包含所有元素的列表和描述索引之间关系的元组的第二个列表，任务是输出一个字典，该字典显示从第一个列表到列表中每个其他元素的关系。
这类问题在编码竞赛中经常遇到。
下面是一些实现上述任务的方法。

```py
Input:
indices = ['x','y','z','w','t','r']
relation =[('x', 'y'), ('x', 'z'), ('x', 'w'), ('y', 'z'), ('y', 'w'), ('z', 'w')]
Output:
{'x': ['y', 'z', 'w'], 'y': ['x', 'z', 'w'], 'z': ['x', 'y', 'w'], 
'w': ['x', 'y', 'z'], 't': [], 'r': []}

```

**方法#1:使用迭代**是解决任何任务最简单的方法

```py
#Python code to convert list of tuple into dictionary showing 
#relation of every element from first list to every other element in the list.

#List initialization
indices = ['x','y','z','w','t','r']
relation =[('x', 'y'), ('x', 'z'), ('x', 'w'), ('y', 'z'), ('y', 'w'), ('z', 'w')]

#dictionary initialization
Output = {}

#Iteration 
for elem in indices:
     temp= []
     for rel in relation:
          if elem in rel:
               if elem == rel[0]:
                    temp.append(rel[1])
               else:
                    temp.append(rel[0])

     Output[elem] = temp
     temp = []

print("Initial list of tuple is :")
print(relation)
print("Converted dictionary of list :")
print(Output)
```

```py
Output :
Initial list of tuple is :
[('x', 'y'), ('x', 'z'), ('x', 'w'), ('y', 'z'), ('y', 'w'), ('z', 'w')]
Converted dictionary of list :
{'w': ['x', 'y', 'z'], 'r': [], 'x': ['y', 'z', 'w'], 't': [], 
'y': ['x', 'z', 'w'], 'z': ['x', 'y', 'w']}

```

**方法 2:使用 networkx** 是将元组列表转换为字典的最简单、最短的
方法

```py
#Python code to convert list of tuple into dictionary showing 
#relation of every element from first list to every other element in the list.

#Importing
import networkx as nx 

#List initialization
indices = ['x','y','z','w','t','r']
relation =[('x', 'y'), ('x', 'z'), ('x', 'w'), ('y', 'z'), ('y', 'w'), ('z', 'w')]

#dictionary initialization
Output = {}

#Using networkx to solve 
temp=nx.Graph(relation)
temp.add_nodes_from(indices)
Output = nx.to_dict_of_lists(temp)

#Printing
print("Initial list of tuple is :")
print(relation)
print("Converted dictionary of list :")
print(Output)
```

```py
Output :
Initial list of tuple is :
[('x', 'y'), ('x', 'z'), ('x', 'w'), ('y', 'z'), ('y', 'w'), ('z', 'w')]
Converted dictionary of list :
{'w': ['x', 'y', 'z'], 'r': [], 'x': ['y', 'z', 'w'], 't': [], 
'y': ['x', 'z', 'w'], 'z': ['x', 'y', 'w']}

```

**方法 3:使用 itertools 和 groupby** 是将元组列表转换为字典的另一种方法。

```py
#Python code to convert list of tuple into dictionary showing 
#relation of every element from first list to every other element in the list.

#Importing
from itertools import groupby
from operator import itemgetter

#List initialization
indices = ['x','y','z','w','t','r']
relation =[('x', 'y'), ('x', 'z'), ('x', 'w'), ('y', 'z'), ('y', 'w'), ('z', 'w')]

#Using itertools.groupby and maps
edge = relation + [tuple(reversed(pair)) for pair in relation]
st = itemgetter(0)
end = itemgetter(1)
groups = groupby(sorted(edge), key=st)
mapping = {vertex: list(map(end, edges)) for vertex, edges in groups}
from collections import defaultdict

#Output list
Output = defaultdict(list, mapping)
Output = dict(mapping)
Output.update({vertex: [] for vertex in indices if vertex not in mapping})

#Printing
print("Initial list of tuple is :")
print(relation)
print("Converted dictionary of list :")
print(Output)
```

```py
Output :
Initial list of tuple is :
[('x', 'y'), ('x', 'z'), ('x', 'w'), ('y', 'z'), ('y', 'w'), ('z', 'w')]
Converted dictionary of list :
{'w': ['x', 'y', 'z'], 'r': [], 'x': ['y', 'z', 'w'], 't': [], 
'y': ['x', 'z', 'w'], 'z': ['x', 'y', 'w']}

```