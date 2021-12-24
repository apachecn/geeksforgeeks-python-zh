# Python |从字典/列表中创建数据框

> 原文:[https://www . geesforgeks . org/python-creating-data frame-from-dict-of-narray-list/](https://www.geeksforgeeks.org/python-creating-dataframe-from-dict-of-narray-lists/)

众所周知，熊猫是数据分析的绝佳工具。最重要的数据类型之一是 dataframe。它是一个二维标记的数据结构，具有可能不同类型的列。它一般是熊猫最常用的对象。
[熊猫数据框](https://www.geeksforgeeks.org/python-pandas-dataframe/)可以通过多种方式创建。让我们来讨论一下如何使用数据字典(或列表)创建熊猫数据帧。
我们试着用几个例子来更好的理解。
**代码#1:**

## 蟒蛇 3

```
# Python code demonstrate creating
# DataFrame from dict narray / lists
# By default addresses.

import pandas as pd

# initialise data of lists.
data = {'Category':['Array', 'Stack', 'Queue'],
        'Marks':[20, 21, 19]}

# Create DataFrame
df = pd.DataFrame(data)

# Print the output.
print(df )
```

**Output:** 

```
Category  Marks
0    Array     20
1    Stack     21
2    Queue     19
```

**注意:**要从 narray/list 的 dict 创建 DataFrame，所有 narray 必须具有相同的长度。如果传递了索引，那么长度索引应该等于数组的长度。如果没有传递索引，那么默认情况下，索引将是范围(n)，其中 n 是数组长度。

**代码#2:**

## 蟒蛇 3

```
# Python code demonstrate creating
# DataFrame from dict narray / lists
# By default addresses.

import pandas as pd

# initialise data of lists.
data = {'Category':['Array', 'Stack', 'Queue'],
        'Student_1':[20, 21, 19], 'Student_2':[15, 20, 14]}

# Create DataFrame
df = pd.DataFrame(data)

# Print the output.
print(df.transpose())
```

**Output:** 

```
              0      1      2
Category   Array  Stack  Queue
Student_1     20     21     19
Student_2     15     20     14
```

**代码#3:** 向数据框
提供索引列表

## 蟒蛇 3

```
# Python code demonstrate creating
# DataFrame from dict narray / lists
# By default addresses.

import pandas as pd

# initialise data of lists.
data = {'Area':['Array', 'Stack', 'Queue'],
        'Student_1':[20, 21, 19], 'Student_2':[15, 20, 14]}

# Create DataFrame
df = pd.DataFrame(data, index =['Cat_1', 'Cat_2', 'Cat_3'])

# Print the output.
print(df)
```

**Output:** 

```
        Area  Student_1  Student_2
Cat_1  Array         20         15
Cat_2  Stack         21         20
Cat_3  Queue         19         14
```