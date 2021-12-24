# 使用给定的频率列表

生成列表

> 原文:[https://www . geesforgeks . org/generate-a-list-使用给定频率-list/](https://www.geeksforgeeks.org/generate-a-list-using-given-frequency-list/)

给定一个列表，任务是从给定列表中生成另一个包含从 *0 到 n* 的数字的列表，该列表的每个元素都是所生成列表中数字的频率。

```
Input: freq = [1, 4, 3, 5]
Output: [0, 1, 1, 1, 1, 2, 2, 2, 3, 3, 3, 3, 3]

Explanation:
Number = 0
Input[0] = 1 Output = [0]

Number =1
Input[1] = 4 Output = [0, 1, 1, 1, 1] (repeats 1 four times)

Number =2
Input[2] = 3  Output = [0, 1, 1, 1, 1, 2, 2, 2] (repeats 2 three times)

Number =3
Input[3] = 5  Output = [0, 1, 1, 1, 1, 2, 2, 2, 3, 3, 3, 3, 3] (repeats 3 five times)

```

以下是实现上述任务的一些方法。

**方法#1:使用迭代**

```
# Python code to generate list containing numbers from 0 to 'n'
# having frequency of no from another list

# List initialisation
Input = [1, 4, 3, 5]
Output = []

# Number initialisation
no = 0

# using iteration
for rep in Input:
    for elem in range(rep):
        Output.append(no)
    no += 1

# printing output
print(Output) 
```

**Output:**

```
[0, 1, 1, 1, 1, 2, 2, 2, 3, 3, 3, 3, 3]

```

**方法 2:使用列举和列表理解**

```
# Python code to generate list containing numbers from 0 to 'n'
# having frequency of no from another list

# List initialisation
Input = [1, 4, 3, 5]

# Using enumerate and list comprehension
Output = [no for no, rep in enumerate(Input)
                     for elem in range(rep)]

# Printing output
print(Output) 
```

**Output:**

```
[0, 1, 1, 1, 1, 2, 2, 2, 3, 3, 3, 3, 3]

```

**方法 3:使用枚举和链**

```
# Python code to generate list containing numbers from 0 to 'n'
# having frequency of no from another list

# List initialisation
Input = [1, 4, 3, 5]

# Importing
from itertools import repeat, chain

# Using chain and enumerate
Output = list(chain.from_iterable((repeat(x, y))
                  for x, y in enumerate(Input)))

# Printing output
print(Output) 
```

**Output:**

```
[0, 1, 1, 1, 1, 2, 2, 2, 3, 3, 3, 3, 3]

```