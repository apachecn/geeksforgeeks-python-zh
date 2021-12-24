# Python |用空列表初始化字典

> 原文:[https://www . geesforgeks . org/python-initiating-dictionary-with-empty-list/](https://www.geeksforgeeks.org/python-initializing-dictionary-with-empty-lists/)

在 python 中，人们通常会遇到必须使用字典来存储列表的情况。但是在这些情况下，人们通常会检查第一个元素，然后在它出现时创建一个对应于 key 的列表。但是它一直想要一个初始化字典的方法。带列表的钥匙。让我们讨论实现这个特殊任务的某些方法。

**方法#1:使用字典理解**
这是最受欢迎的初始化方法。在这种方法中，我们创建所需的键数，然后在继续创建键的同时初始化空列表，以便于之后的追加操作而不会出错。

```
# Python3 code to demonstrate 
# to initialize dictionary with list 
# using dictionary comprehension

# using dictionary comprehension to construct
new_dict = {new_list: [] for new_list in range(4)}

# printing result
print ("New dictionary with empty lists as keys : " + str(new_dict))
```

**输出:**

```
New dictionary with empty lists as keys : {0: [], 1: [], 2: [], 3: []}

```

**方法 2:使用`fromkeys()`**
`fromkeys()`可以通过指定额外的空列表作为参数和需要作为正在制作的字典的关键字的元素范围来执行此操作。

```
# Python3 code to demonstrate 
# to initialize dictionary with list 
# using fromkeys()

# using fromkeys() to construct
new_dict = dict.fromkeys(range(4), [])

# printing result
print ("New dictionary with empty lists as keys : " + str(new_dict))
```

**输出:**

```
New dictionary with empty lists as keys : {0: [], 1: [], 2: [], 3: []}

```

**方法#3:使用 defaultdict**
这是最 pythonic 化的方式，也是无错误的方式，使用任何键都不需要初始化它的值，必须告诉它所有键的默认容器的类型，然后相应地评估操作和结构。

```
# Python3 code to demonstrate 
# to initialize dictionary with list 
# using defaultdict
from collections import defaultdict

# initializing dict with lists
new_dict = defaultdict(list)

# performing append
# shows no error
new_dict[0].append('GeeksforGeeks')

# printing result
print ("New dictionary created : " + str(dict(new_dict)))
```

**输出:**

```
New dictionary created : {0: ['GeeksforGeeks']}

```

**方法#4:使用 setdefault**
`setdefault()`可以通过指定理解范围内的键值对来执行此操作。该方法消除了方法#3 中所要求的导入模块的需要。

```
# Python3 code to demonstrate 
# to initialize dictionary with list 
# using setdefault

# initializing dict with lists
new_dict = {}
[new_dict.setdefault(x, []) for x in range(4)]

# performing append
# shows no error
new_dict[0].append('GeeksforGeeks')

# printing result
print ("New dictionary created : " + str(dict(new_dict)))
```

**输出:**

```
New dictionary created : {0: ['GeeksforGeeks'], 1: [], 2: [], 3: []}

```

**方法五:使用内置:dict 和 zip**
内置函数`dict, zip`结合列表理解可以达到预期的效果。

```
# Python3 code to demonstrate 
# use of dict() and zip() built-ins to demonstrate
# initializing dictionary with list 

keys = range(4)
new_dict = dict(zip(keys, ([] for _ in keys)))

print(new_dict)# performing append
# shows no error
new_dict[0].append('GeeksforGeeks')

# printing result
print ("New dictionary created : " + str(dict(new_dict)))
```

**输出:**

```
New dictionary created : {0: ['GeeksforGeeks'], 1: [], 2: [], 3: []}

```