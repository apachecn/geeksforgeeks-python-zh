# Python |查找列表中最频繁的元素

> 原文:[https://www . geesforgeks . org/python-在列表中查找最频繁的元素/](https://www.geeksforgeeks.org/python-find-most-frequent-element-in-a-list/)

给定一个列表，找出其中最常见的元素。如果存在出现次数最多的多个元素，请打印其中任何一个。

**示例:**

```py
Input : [2, 1, 2, 2, 1, 3]
Output : 2

Input : ['Dog', 'Cat', 'Dog']
Output : Dog
```

**方法#1 :** 天真方法
这是一种蛮力方法，我们利用 for 循环来计算每个元素的频率。如果当前频率大于先前频率，则更新计数器并存储元素。

## 蟒蛇 3

```py
# Program to find most frequent
# element in a list

def most_frequent(List):
    counter = 0
    num = List[0]

    for i in List:
        curr_frequency = List.count(i)
        if(curr_frequency> counter):
            counter = curr_frequency
            num = i

    return num

List = [2, 1, 2, 2, 1, 3]
print(most_frequent(List))
```

**Output:** 

```py
2
```

**方法# 2:**python 天真方法
制作一组列表，以便删除重复的元素。然后找出集合中每个元素出现的最高次数，从而找出最大值。

## 蟒蛇 3

```py
# Program to find most frequent
# element in a list
def most_frequent(List):
    return max(set(List), key = List.count)

List = [2, 1, 2, 2, 1, 3]
print(most_frequent(List))
```

**Output:** 

```py
2
```

**方法#3 :** 使用[计数器](https://www.geeksforgeeks.org/counters-in-python-set-1/)
使用 Python 计数器返回列表中每个元素的计数。因此，我们只需使用 most_common()方法找到最常见的元素。

## 蟒蛇 3

```py
# Program to find most frequent
# element in a list

from collections import Counter

def most_frequent(List):
    occurence_count = Counter(List)
    return occurence_count.most_common(1)[0][0]

List = [2, 1, 2, 2, 1, 3]
print(most_frequent(List))
```

**Output:** 

```py
2
```

**方法#4 :** 通过查找模式
查找最频繁的元素意味着查找列表的模式。因此，我们使用统计学中的模式方法。

## 蟒蛇 3

```py
import statistics
from statistics import mode

def most_common(List):
    return(mode(List))

List = [2, 1, 2, 2, 1, 3]
print(most_common(List))
```

**Output:** 

```py
2
```

**方法#5 :** 使用 python 字典
使用 Python 字典将元素保存为键，将其频率保存为值，从而找到最频繁的元素。

## 蟒蛇 3

```py
# Program to find most frequent
# element in a list

def most_frequent(List):
    dict = {}
    count, itm = 0, ''
    for item in reversed(List):
        dict[item] = dict.get(item, 0) + 1
        if dict[item] >= count :
            count, itm = dict[item], item
    return(itm)

List = [2, 1, 2, 2, 1, 3]
print(most_frequent(List))
```

**Output:** 

```py
2
```

**方法#6 :** 利用熊猫库。
在多重价值不断重复的情况下。打印所有值。

## 蟒蛇 3

```py
import pandas as pd
List = [2, 1, 2, 2, 1, 3, 1]

# Create a panda DataFrame using the list
df=pd.DataFrame({'Number': List})

# Creating a new dataframe to store the values
# with appropriate column name
# value_counts() returns the count based on
# the grouped column values
df1 = pd.DataFrame(data=df['Number'].value_counts(), columns=[['Number','Count']])

# The values in the List become the index of the new dataframe.
# Setting these index as a column
df1['Count']=df1['Number'].index

# Fetch the list of frequently repeated columns
list(df1[df1['Number']==df1.Number.max()]['Count'])
```

**Output:** 

```py
[2,1]
```