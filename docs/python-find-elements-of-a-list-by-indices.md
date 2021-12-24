# Python |通过索引查找列表元素

> 原文:[https://www . geesforgeks . org/python-按索引查找列表元素/](https://www.geeksforgeeks.org/python-find-elements-of-a-list-by-indices/)

给定两个包含元素和索引的列表，编写一个 Python 程序，在*列表 2* 中的索引处找到*列表 1* 的元素。

**示例:**

```
Input : lst1 = [10, 20, 30, 40, 50]
        lst2 = [0, 2, 4]
Output : [10, 30, 50]
Explanation: 
Output elements at indices 0, 2 and 4 i.e 10, 30 and 50 respectively. 

Input : lst1 = ['Hello', 'geeks', 'for', 'geeks']
        lst2 = [1, 2, 3]
Output : ['geeks', 'for', 'geeks']

```

下面是一些完成上述任务的皮托尼方法。

**方法#1 :** 幼稚(列表理解)

找到所需元素的第一种方法是使用列表理解。我们遍历“lst2”，对于每个 i <sup>第</sup>个元素，我们输出 lst1[i]。

```
# Python3 program to Find elements of a 
# list by indices present in another list

def findElements(lst1, lst2):
    return [lst1[i] for i in lst2]

# Driver code
lst1 = [10, 20, 30, 40, 50]
lst2 = [0, 2, 4]
print(findElements(lst1, lst2))
```

**Output:**

```
[10, 30, 50]

```

**方法 2 :** 使用 Python `map()`

我们也可以使用 Python `map()`方法，在 *lst2* 上应用`lst1.__getitem__` 函数，该函数为 lst2 的每个元素“I”返回 `lst1[i]` 。

```
# Python3 program to Find elements of a 
# list by indices present in another list

def findElements(lst1, lst2):
    return list(map(lst1.__getitem__, lst2))

# Driver code
lst1 = [10, 20, 30, 40, 50]
lst2 = [0, 2, 4]
print(findElements(lst1, lst2))
```

**Output:**

```
[10, 30, 50]

```

**使用`itemgetter()`接近#3 :**

```
# Python3 program to Find elements of a 
# list by indices present in another list
from operator import itemgetter 

def findElements(lst1, lst2):
    return list((itemgetter(*lst2)(lst1)))

# Driver code
lst1 = [10, 20, 30, 40, 50]
lst2 = [0, 2, 4]
print(findElements(lst1, lst2))
```

**Output:**

```
[10, 30, 50]

```

**使用`numpy`接近#4 :**

```
# Python3 program to Find elements of a 
# list by indices present in another list
import numpy as np 

def findElements(lst1, lst2):
    return list(np.array(lst1)[lst2])

# Driver code
lst1 = [10, 20, 30, 40, 50]
lst2 = [0, 2, 4]
print(findElements(lst1, lst2))
```

**Output:**

```
[10, 30, 50]

```