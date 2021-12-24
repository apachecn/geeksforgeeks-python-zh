# Python |在给定字符串列表中的每个 k 个字母后插入值

> 原文:[https://www . geesforgeks . org/python-给定字符串列表中每个 k 字母后插入值/](https://www.geeksforgeeks.org/python-insert-value-after-each-k-letters-in-given-list-of-string/)

给定一个字符串列表，编写一个 Python 程序，在给定的字符串列表中的每个 k 个字母后插入一些字母。

众所周知，在列表中插入元素是很常见的，但有时我们需要通过考虑每个字母来操作字符串列表，并以固定的频率插入一些重复的元素。让我们看看如何使用 Python 实现这个任务。

**方法#1:** 使用枚举()方法

```py
# Python program to insert value after
# each k letters in given list of string
list1 = ['p', 'y', 't', 'h', 'o', 'n'] 

# printing original list 
print ("Original list : " + str(list1)) 

# initializing k 
k = 'G'

# initializing N 
N = 2

# using join() + enumerate() 
# inserting K after every Nth number 
output = list(''.join(i + k * (N % 2 == 1) 
        for N, i in enumerate(list1))) 

# printing result 
print ("The lists after insertion : " + str(output)) 
```

**Output:**

```py
Original list : ['p', 'y', 't', 'h', 'o', 'n']
The lists after insertion : ['p', 'y', 'G', 't', 'h', 'G', 'o', 'n', 'G']

```

**方法 2:** 使用 itertools

```py
# Python program to insert value after
# each k letters in given list of string
from itertools import chain 

list1 = ['p', 'y', 't', 'h', 'o', 'n'] 

# printing original list 
print ("Original list : " + str(list1)) 

# initializing k  
k = 'x'

# initializing N 
N = 3

# inserting K after every Nth number  
output = list(chain(*[list1[i : i + N] + [k]  
              if len(list1[i : i + N]) == N  else list1[i : i + N]  
              for i in range(0, len(list1), N)])) 

# printing result 
print ("The lists after insertion : " + str(output)) 
```

**Output:**

```py
Original list : ['p', 'y', 't', 'h', 'o', 'n']
The lists after insertion : ['p', 'y', 't', 'x', 'h', 'o', 'n', 'x']

```