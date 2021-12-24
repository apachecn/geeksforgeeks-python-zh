# python–etrtools . filter LSE()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-etrtools-filter LSE/

在 Python 中，Itertools 是内置的模块，允许我们以有效的方式处理迭代器。它们使得遍历像列表和字符串这样的数据项变得非常容易。一个这样的 itertools 函数是 **filterfalse()。**

**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

## filterfalse()功能

这个迭代器只打印为传递的函数返回 false 的值。

**语法:**

```
filterfalse(function or None, sequence) --> filterfalse object
```

**参数:**这个方法包含两个参数，第一个参数是 function 或者 None，第二个参数是 list of integer。
**返回值:**这个方法只返回传递函数返回 false 的值。

**例 1:**

```
# Python program to demonstrate 
# the working of filterfalse 
import itertools
from itertools import filterfalse 

# function is a None
for i in filterfalse(None, range(20)):  
    print(i) 

li = [2, 4, 5, 7, 8, 10, 20]  

# Slicing the list 
print(list(itertools.filterfalse(None, li)))  
```

**输出:**

```
0
[]
```

**例 2:**

```
# Python program to demonstrate 
# the working of filterfalse 
import itertools
from itertools import filterfalse 

def filterfalse(y):
    return (y > 5)

li = [2, 4, 5, 7, 8, 10, 20]  

# Slicing the list 
print(list(itertools.filterfalse(filterfalse, li)))
```

**输出:**

```
[2, 4, 5]

```

**例 3:**

```
# Python program to demonstrate 
# the working of filterfalse 
import itertools
from itertools import filterfalse 

li = [2, 4, 5, 7, 8, 10, 20]  

# Slicing the list 
print (list(itertools.filterfalse(lambda x : x % 2 == 0, li))) 
```

**输出:**

```
[5, 7]

```