# Python |删除 k 个字符后查找所有可能的子串

> 原文:[https://www . geeksforgeeks . org/python-查找-所有可能的子字符串-删除后-k-characters/](https://www.geeksforgeeks.org/python-find-all-possible-substrings-after-deleting-k-characters/)

给定一个字符串和一个整数 k，编写一个 Python 程序，在删除 k 个字符后，找到给定字符串的所有可能的子字符串。

**示例:**

```
Input : geeks, k = 1
Output : {'gees', 'eeks', 'geks', 'geek'}

Input : dog, k = 1
Output : {'do', 'dg', 'og'}

```

**方法#1 :** 朴素方法
这是删除 k 个字符后寻找所有可能子串的递归朴素方法。首先，我们分别用 0、字符串长度和 0 初始化*开始、结束*和索引变量。我们创建一个临时列表，比如说“ *temp* ”，它一个接一个地存储所有输出。我们从`temp[]`中的第一个索引开始，一个接一个地固定这个索引处的元素，并对剩余的索引重复。

```
# Python3 program to Find all combinations 
# of string after deleting k characters
list = []

def findCombinations(str, temp, start, end, index, k): 

    if (index == k): 
        item = ''

        for j in range(k): 
            item += temp[j]
        list.append(item)
        return; 

    i = start; 
    while(i <= end and end - i + 1 >= k - index): 
        temp[index] = str[i]
        findCombinations(str, temp, i + 1, 
                        end, index + 1, k); 
        i += 1; 

# Driver Code
str = 'geeks'
k = 1
temp = [0]*(len(str)-k)
s, e = 0, len(str)-1

findCombinations(str, temp, s, e, 0, len(str)-k)
print(set(list))
```

**Output:**

```
{'eeks', 'gees', 'geks', 'geek'}

```

**方法 2 :** 使用 Itertools
Python 模块 Itertools 给出了一个函数`combination()`，该函数采用字符串和长度给出字符串的所有可能组合。

```
# Python3 program to Find all combinations 
# of string after deleting k characters
from itertools import combinations

def findCombinations(str, k):
    l = len(str)
    return set([''.join(i) for i in combinations(str, l - k)])

# Driver Code
str = 'geeks'
k = 1
print(findCombinations(str, k))
```

**Output:**

```
{'geek', 'eeks', 'geks', 'gees'}

```