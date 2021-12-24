# Python 中的理解

> 原文:[https://www.geeksforgeeks.org/comprehensions-in-python/](https://www.geeksforgeeks.org/comprehensions-in-python/)

Python 中的理解为我们构造新的序列(如列表、集合、字典等)提供了一种简洁明了的方法。)使用已经定义的序列。Python 支持以下 4 种类型的理解:

*   列表理解
*   字典理解
*   集合理解
*   发电机理解

### 列表理解:

列表理解为创建新列表提供了一种优雅的方式。以下是列表理解的基本结构:

> output _ list =[*output _ exp*为*输入 _list* 中的 *var* 如果( *var* 满足此条件)】

请注意，列表理解可能包含也可能不包含 if 条件。列表理解可以包含多个(嵌套列表理解)。

**示例#1:** 假设我们想要创建一个输出列表，其中只包含输入列表中出现的偶数。让我们看看如何使用*进行循环*和*列出理解*并决定哪种方法更适合。

```py
# Constructing output list WITHOUT
# Using List comprehensions
input_list = [1, 2, 3, 4, 4, 5, 6, 7, 7]

output_list = []

# Using loop for constructing output list
for var in input_list:
    if var % 2 == 0:
        output_list.append(var)

print("Output List using for loop:", output_list)
```

**输出:**

```py
Output List using for loop: [2, 4, 4, 6]
```

```py
# Using List comprehensions
# for constructing output list

input_list = [1, 2, 3, 4, 4, 5, 6, 7, 7]

list_using_comp = [var for var in input_list if var % 2 == 0]

print("Output List using list comprehensions:",
                               list_using_comp)
```

**输出:**

```py
Output List using list comprehensions: [2, 4, 4, 6]
```

**示例#2:** 假设我们想要创建一个输出列表，其中包含从 1 到 9 的所有数字的平方。让我们看看如何使用循环和列表理解来做到这一点。

```py
# Constructing output list using for loop
output_list = []
for var in range(1, 10):
    output_list.append(var ** 2)

print("Output List using for loop:", output_list)
```

**输出:**

```py
Output List using for loop: [1, 4, 9, 16, 25, 36, 49, 64, 81]
```

```py
# Constructing output list
# using list comprehension
list_using_comp = [var**2 for var in range(1, 10)]

print("Output List using list comprehension:", 
                              list_using_comp)
```

**输出:**

```py
Output List using list comprehension: [1, 4, 9, 16, 25, 36, 49, 64, 81]
```

### 字典理解:

扩展列表理解的概念，我们也可以使用字典理解来创建字典。字典理解的基本结构如下。

> output_dict = {key:如果(key，value 满足此条件)}则为*可迭代*中的(key，value)值

**示例#1:** 假设我们想要创建一个输出字典，它只包含作为键出现在输入列表中的奇数，以及作为值出现在它们的立方体中的奇数。让我们看看如何使用循环和字典理解来做到这一点。

```py
input_list = [1, 2, 3, 4, 5, 6, 7]

output_dict = {}

# Using loop for constructing output dictionary
for var in input_list:
    if var % 2 != 0:
        output_dict[var] = var**3

print("Output Dictionary using for loop:",
                             output_dict )
```

**输出:**

```py
Output Dictionary using for loop: {1: 1, 3: 27, 5: 125, 7: 343}
```

```py
# Using Dictionary comprehensions
# for constructing output dictionary

input_list = [1,2,3,4,5,6,7]

dict_using_comp = {var:var ** 3 for var in input_list if var % 2 != 0}

print("Output Dictionary using dictionary comprehensions:",
                                           dict_using_comp)
```

**输出:**

```py
Output Dictionary using dictionary comprehensions: {1: 1, 3: 27, 5: 125, 7: 343}

```

**示例#2:** 给定两个包含州名及其对应首都的列表，构造一个字典，将各州与其各自的首都进行映射。让我们看看如何使用循环和字典理解来做到这一点。

```py
state = ['Gujarat', 'Maharashtra', 'Rajasthan']
capital = ['Gandhinagar', 'Mumbai', 'Jaipur']

output_dict = {}

# Using loop for constructing output dictionary
for (key, value) in zip(state, capital):
    output_dict[key] = value

print("Output Dictionary using for loop:",
                              output_dict)
```

**输出:**

```py
Output Dictionary using for loop: {'Gujarat': 'Gandhinagar',
                                   'Maharashtra': 'Mumbai', 
                                   'Rajasthan': 'Jaipur'}
```

```py
# Using Dictionary comprehensions
# for constructing output dictionary

state = ['Gujarat', 'Maharashtra', 'Rajasthan']
capital = ['Gandhinagar', 'Mumbai', 'Jaipur']

dict_using_comp = {key:value for (key, value) in zip(state, capital)}

print("Output Dictionary using dictionary comprehensions:", 
                                           dict_using_comp)
```

**输出:**

```py
Output Dictionary using dictionary comprehensions: {'Rajasthan': 'Jaipur',
                                                    'Maharashtra': 'Mumbai',
                                                    'Gujarat': 'Gandhinagar'}
```

### 设定理解:

集合理解与列表理解非常相似。它们之间唯一的区别是集合理解使用了花括号`{ }`。让我们看下面的例子来理解集合理解。

**示例#1 :** 假设我们想要创建一个输出集，该输出集只包含输入列表中出现的偶数。请注意，set 将丢弃所有重复的值。让我们看看如何使用循环和集合理解来做到这一点。

```py
input_list = [1, 2, 3, 4, 4, 5, 6, 6, 6, 7, 7]

output_set = set()

# Using loop for constructing output set
for var in input_list:
    if var % 2 == 0:
        output_set.add(var)

print("Output Set using for loop:", output_set)
```

**输出:**

```py
Output Set using for loop: {2, 4, 6}
```

```py
# Using Set comprehensions 
# for constructing output set

input_list = [1, 2, 3, 4, 4, 5, 6, 6, 6, 7, 7]

set_using_comp = {var for var in input_list if var % 2 == 0}

print("Output Set using set comprehensions:",
                              set_using_comp)
```

**输出:**

```py
Output Set using set comprehensions: {2, 4, 6}
```

### 发电机理解:

生成器理解与列表理解非常相似。它们之间的一个区别是生成器理解使用圆括号，而列表理解使用方括号。它们之间的主要区别是生成器不会为整个列表分配内存。相反，它们一个接一个地生成每个值，这就是为什么它们是内存高效的。让我们看下面的例子来理解发电机的理解:

```py
input_list = [1, 2, 3, 4, 4, 5, 6, 7, 7]

output_gen = (var for var in input_list if var % 2 == 0)

print("Output values using generator comprehensions:", end = ' ')

for var in output_gen:
    print(var, end = ' ')
```

**输出:**

```py
Output values using generator comprehensions: 2 4 4 6 

```