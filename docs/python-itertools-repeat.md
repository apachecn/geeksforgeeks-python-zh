# Python–ITER tools . repeat()

> 原文:[https://www.geeksforgeeks.org/python-itertools-repeat/](https://www.geeksforgeeks.org/python-itertools-repeat/)

Python 的 Itertool 是一个模块，它提供了各种在迭代器上工作的函数来产生复杂的迭代器。这个模块作为一个快速、内存高效的工具，可以单独使用，也可以组合使用，形成迭代器代数。

**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

## 重复()

`itertools.repeat()`属于[无限迭代器](https://www.geeksforgeeks.org/python-itertools/#infinite)的范畴。在`repeat()`中我们给出数据并给出数字，数据会重复多少次。如果我们不指定数字，它会重复无限次。在 repeat()中，不会为每个变量创建内存空间。相反，它只创建一个变量，并重复相同的变量。

> **语法:**重复(val，num)
> 
> **参数:**
> **val:** 要打印的值。
> **num:** 如果提到可选关键字 num，则重复打印传递值 num 次，否则无限次打印传递值。

**例 1:**

```
# Python code to demonstrate the working of    
# repeat()   

import itertools   

# using repeat() to repeatedly print number   
print ("Printing the numbers repeatedly : ")   
print (list(itertools.repeat(25, 4)))
```

**输出:**

```
Printing the numbers repeatedly : 
[25, 25, 25, 25]

```

**例 2:**

```
# Python code to demonstrate the working of    
# repeat()

import itertools

# using repeat() to repeatedly print string 
print(list(map(str.upper, 
               itertools.repeat('geeksforgeeks', 3))))
```

**输出:**

```
['GEEKSFORGEEKS', 'GEEKSFORGEEKS', 'GEEKSFORGEEKS']

```