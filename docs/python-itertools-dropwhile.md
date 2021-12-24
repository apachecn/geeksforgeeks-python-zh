# python–etrtools . drop while()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-etrtools-drop while/

[Itertools](https://www.geeksforgeeks.org/python-itertools/) 是一个 Python 模块，提供了各种在迭代器上工作的函数，以产生复杂的迭代器。它使代码更快，内存更有效，因此我们看到了更好的性能。这个模块可以单独使用，也可以组合使用，形成迭代器代数。

**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

## Dropwhile()

Python 的`dropwhile()`函数只在`func`之后返回一个迭代器。`false`第一次在争论中回归。

**语法:**

```
dropwhile(func, seq):
```

**例 1:**

```
# Python code to demonstrate the working of   
# dropwhile() 

# Function to be passed
# as an argument
def is_positive(n):
    return n > 0 

value_list =[5, 6, -8, -4, 2]
result = list(itertools.dropwhile(is_positive, value_list)) 

print(result) 
```

**输出:**

```
[-8, -4, 2]
```

**例 2:**

```
# Python code to demonstrate the working of   
# dropwhile() 

import itertools 

# initializing list   
li = [2, 4, 5, 7, 8]  

# using dropwhile() to start displaying after condition is false  
print ("The values after condition returns false : ", end ="")  
print (list(itertools.dropwhile(lambda x : x % 2 == 0, li))) 
```

**输出:**

```
The values after condition returns false : [5, 7, 8]
```