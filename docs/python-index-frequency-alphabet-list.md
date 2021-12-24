# Python–索引频率字母表

> 原文:[https://www . geesforgeks . org/python-index-frequency-alphabet-list/](https://www.geeksforgeeks.org/python-index-frequency-alphabet-list/)

创建一个字符串列表，其中每个字符与其位置号重复。

**方法#1:使用 ascii _ 小写+order()+循环**

在这种情况下，获取索引的任务是使用 order()完成的，ascii 小写()用于提取字母。循环用于为每个字母执行任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Index Frequency Alphabet List
# Using ascii_lowercase + ord() + loop
from string import ascii_lowercase

# extracting start index
strt_idx = ord('a') - 1

res = []
for ele in ascii_lowercase:

    # multiplying Frequency
    res.append(ele * (ord(ele) - strt_idx))

# printing result
print("The constructed list : " + str(res))
```

**Output**

```py
The constructed list : ['a', 'bb', 'ccc', 'dddd', 'eeeee', 'ffffff', 'ggggggg', 'hhhhhhhh', 'iiiiiiiii', 'jjjjjjjjjj', 'kkkkkkkkkkk', 'llllllllllll', 'mmmmmmmmmmmmm', 'nnnnnnnnnnnnnn', 'ooooooooooooooo', 'pppppppppppppppp', 'qqqqqqqqqqqqqqqqq', 'rrrrrrrrrrrrrrrrrr', 'sssssssssssssssssss', 'tttttttttttttttttttt', 'uuuuuuuuuuuuuuuuuuuuu', 'vvvvvvvvvvvvvvvvvvvvvv', 'wwwwwwwwwwwwwwwwwwwwwww', 'xxxxxxxxxxxxxxxxxxxxxxxx', 'yyyyyyyyyyyyyyyyyyyyyyyyy', 'zzzzzzzzzzzzzzzzzzzzzzzzzz']
```

**方法 2:使用列表理解+ascii _ 小写+order()**

本文采用列表理解来解决这个问题。这是上述方法的简写。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Index Frequency Alphabet List
# Using list comprehension + ascii_lowercase + ord()
from string import ascii_lowercase

# extracting start index
strt_idx = ord('a') - 1

# list comprehension to solve as one liner
res = [ele * (ord(ele) - strt_idx) for ele in ascii_lowercase]

# printing result
print("The constructed list : " + str(res))
```

**Output**

```py
The constructed list : ['a', 'bb', 'ccc', 'dddd', 'eeeee', 'ffffff', 'ggggggg', 'hhhhhhhh', 'iiiiiiiii', 'jjjjjjjjjj', 'kkkkkkkkkkk', 'llllllllllll', 'mmmmmmmmmmmmm', 'nnnnnnnnnnnnnn', 'ooooooooooooooo', 'pppppppppppppppp', 'qqqqqqqqqqqqqqqqq', 'rrrrrrrrrrrrrrrrrr', 'sssssssssssssssssss', 'tttttttttttttttttttt', 'uuuuuuuuuuuuuuuuuuuuu', 'vvvvvvvvvvvvvvvvvvvvvv', 'wwwwwwwwwwwwwwwwwwwwwww', 'xxxxxxxxxxxxxxxxxxxxxxxx', 'yyyyyyyyyyyyyyyyyyyyyyyyy', 'zzzzzzzzzzzzzzzzzzzzzzzzzz']
```