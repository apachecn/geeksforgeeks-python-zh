# python—http 工具。交换()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-etrtools-switchions/

[Itertool](https://www.geeksforgeeks.org/python-itertools/) 是 Python 提供的一个模块，用于创建迭代器以实现高效的循环。它还提供了与迭代器一起工作的各种特性或函数，以生成复杂的迭代器，并帮助我们轻松高效地解决时间和内存方面的问题。Itertools 模块为我们提供了各种方法来操作我们正在遍历的序列。

**该模块提供的不同类型的迭代器有:**

*   [无限迭代器](https://www.geeksforgeeks.org/python-itertools/#infinite)
*   [终止于最短输入序列的迭代器](https://www.geeksforgeeks.org/python-itertools/#terminate)
*   [组合迭代器](https://www.geeksforgeeks.org/python-itertools/#combine)

**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

## itertools()

`Itertools.permutation()`功能属于组合生成器。用于简化组合结构(如排列、组合和笛卡尔乘积)的递归生成器称为组合迭代器。

如单词“置换”所理解的，它指的是集合或串可以被排序或排列的所有可能的组合。类似地，这里`itertool.permutations()`方法为我们提供了迭代器可能存在的所有可能的排列，并且所有元素都被假定为基于位置而不是基于值或类别是唯一的。所有这些排列都是按照字典顺序排列的。函数`itertool.permutations()`将一个迭代器和“r”(需要的排列长度)作为输入，并假设“r”是迭代器的默认长度(如果没有提到的话)，并返回每个长度“r”的所有可能的排列。

**语法:**

```py
Permutations(iterator, r)

```

**实施例 1:-**

```py
from itertools import permutations 

a = "GeEK"

# no length entered so default length
# taken as 4(the length of string GeEK)
p = permutations(a) 

# Print the obtained permutations 
for j in list(p): 
    print(j) 
```

**输出:-**

```py
('G', 'e', 'E', 'K')
('G', 'e', 'K', 'E')
('G', 'E', 'e', 'K')
('G', 'E', 'K', 'e')
('G', 'K', 'e', 'E')
('G', 'K', 'E', 'e')
('e', 'G', 'E', 'K')
('e', 'G', 'K', 'E')
('e', 'E', 'G', 'K')
('e', 'E', 'K', 'G')
('e', 'K', 'G', 'E')
('e', 'K', 'E', 'G')
('E', 'G', 'e', 'K')
('E', 'G', 'K', 'e')
('E', 'e', 'G', 'K')
('E', 'e', 'K', 'G')
('E', 'K', 'G', 'e')
('E', 'K', 'e', 'G')
('K', 'G', 'e', 'E')
('K', 'G', 'E', 'e')
('K', 'e', 'G', 'E')
('K', 'e', 'E', 'G')
('K', 'E', 'G', 'e')
('K', 'E', 'e', 'G')

```

**实施例 2:-**

```py
from itertools import permutations  

print ("All the permutations of the given list is:")   
print (list(permutations([1, 'geeks'], 2)))  
print()  

print ("All the permutations of the given string is:")   
print (list(permutations('AB')))  
print()  

print ("All the permutations of the given container is:")   
print(list(permutations(range(3), 2)))  
```

**输出:-**

```py
All the permutations of the given list is:
[(1, 'geeks'), ('geeks', 1)]

All the permutations of the given string is:
[('A', 'B'), ('B', 'A')]

All the permutations of the given container is:
[(0, 1), (0, 2), (1, 0), (1, 2), (2, 0), (2, 1)]

```