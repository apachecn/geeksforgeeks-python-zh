# Python |查找列表中每个位置给定字符的频率

> 原文:[https://www . geesforgeks . org/python-查找列表中每个位置给定字符的频率/](https://www.geeksforgeeks.org/python-find-frequency-of-given-character-at-every-position-in-list-of-lists/)

给定一个列表列表，任务是在列表列表中子列表的每个位置找到一个字符的频率。

```
Input : lst = [['X', 'Y', 'X'], ['Z', 'Y', 'X'],
               ['Y', 'Y', 'Y'], ['Z', 'Z', 'X'],
               ['Y', 'Z', 'X']], character = 'X'

Output: [0.2, 0.0, 0.8]
```

**说明:**
我们每个子列表中有 3 个元素，我们要在 0、1、2 位置找到‘X’的位置。对于所有子列表中的位置 **0** ，第一个子列表中的–
【x】位于零位置，第二个子列表中的
【z】位于零位置，第三个子列表中的
【y】位于零位置，第四个子列表中的
【z】位于零位置，第五个子列表中的
【y】位于零位置。

因此，我们在所有子列表中的位置 1 有 1 个“x”的出现，因此，出现= 1/5 = .2
对于位置 **1** ，我们在子列表中没有任何“x”的出现，因此，出现= 0/5 = 0。
对于位置 **2** ，我们在子列表中有 4 个“x”的出现，因此出现次数= 4/5 = 0.8

让我们讨论一下可以执行此操作的某些方式。

**方法#1:使用迭代**

```
# Python code to find frequency of a character
# at every position of list in list of lists.

# Input list initialization
Input = [['X', 'Y', 'X'], ['Z', 'Y', 'X'],
         ['Y', 'Y', 'Y'], ['Z', 'Z', 'X'],
         ['Y', 'Z', 'X']]
Output = []

# Character Initialization
character = 'X'

# Output list initialization
for elem in range(len(Input[0])):
    Output.append(0)

# Using iteration
for elem in Input:
    for x, y in enumerate(elem):
        if y == character:
            Output[x]+= 1
for x, y in enumerate(Output):
    Output[x] = y / len(Input)

# Printing
print("Initial list of list is :", Input)
print("Occurrence of 'X' in list is", Output)
```

**Output:**

> 列表初始列表为:[['X '，' Y '，' X']，['Z '，' Y '，' X']，['Y '，' Y '，' Y']，['Z '，' Z '，' X']，['Y '，' Z '，' X ']
> 列表中' X '的出现次数为[0.2，0.0，0.8]

**方法 2:使用 zip**

```
# Python code to find frequency of a character
# at every position of list in list of lists.

# Input list initialization
Input = [['X', 'Y', 'X'], ['Z', 'Y', 'X'],
         ['Y', 'Y', 'Y'], ['Z', 'Z', 'X'],
         ['Y', 'Z', 'X']]

Output = []

# Character initialization
character = 'X'

# Using zip
Output = [elem.count(character)/len(elem)
                 for elem in zip(*Input)]

# Printing
print("Initial list of list is :", Input)
print("Occurrence of 'X' in list is", Output)
```

**Output:**

> 列表初始列表为:[['X '，' Y '，' X']，['Z '，' Y '，' X']，['Y '，' Y '，' Y']，['Z '，' Z '，' X']，['Y '，' Z '，' X ']
> 列表中' X '的出现次数为[0.2，0.0，0.8]

**方法三:利用熊猫**

```
# Python code to find frequency of a character
# at every position of list in list of lists.

import pandas as pd

# Input list initialization
Input = [['X', 'Y', 'X'],
      ['Z', 'Y', 'X'],
      ['Y', 'Y', 'Y'],
      ['Z', 'Z', 'X'],
      ['Y', 'Z', 'X']]

# Defining character
character = 'X'

# using pandas
Output = pd.DataFrame(Input)
Output = Output.where(Output == character, 0).where(Output != character, 1)

# Printing
print("Initial list of list is :", Input)
print("Occurrence of 'X' in list is\n", Output.mean())
```

**Output:**

> 列表初始列表为:[['X '，' Y '，' X']，['Z '，' Y '，' X']，['Y '，' Y '，' Y']，['Z '，' Z '，' X']，['Y '，' Z '，' X ']
> 列表中' X '的出现次数为
> 0 0.2
> 1 0.0
> 2 0.8
> 数据类型:float64