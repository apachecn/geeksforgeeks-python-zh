# Python–字典键的累积平均值

> 原文:[https://www . geeksforgeeks . org/python-累计平均字典键数/](https://www.geeksforgeeks.org/python-cumulative-mean-of-dictionary-keys/)

给定字典列表，我们的任务是编写一个 Python 程序来提取所有键的平均值。

> **输入:** test_list = [{'gfg' : 34，' is' : 8，' best' : 10}，
> 
> {'gfg' : 1，' for' : 10，' geeks' : 9，' and' : 5，' best' : 12}，
> 
> {“极客”:8，“find”:3，“gfg”:3，“best”:8 }]
> 
> **输出:** {'gfg': 12.666666666666，' is': 8，' best': 10，' for': 10，' geeks': 8.5，' and': 5，' find': 3}
> 
> **解释:** best 有 3 个值，10，8 和 12，它们的平均值计算为 10，结果如此。
> 
> **输入:** test_list = [{'gfg' : 34，' is' : 8，' best' : 10}，
> 
> {“gfg”:1，“for”:10，“and”:5，“best”:12 }，
> 
> {“find”:3，“gfg”:3，“best”:8 }]
> 
> **输出:** {'gfg': 12.66666666666，' is': 8，' best': 10，' for': 10，' and': 5，' find': 3}
> 
> **解释:** best 有 3 个值，10，8 和 12，它们的平均值计算为 10，结果如此。

**方法#1:使用** [**的意思是()**](https://www.geeksforgeeks.org/python-statistics-mean-function/) **+** [**循环**](https://www.geeksforgeeks.org/python-for-loops/)

在这种情况下，为了提取每个列表，使用循环，并使用字典对所有值进行求和和存储。平均值随后通过除以每个键的出现次数来提取。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Cumulative Keys Mean in Dictionary List
# Using loop + mean()
from statistics import mean

# initializing list
test_list = [{'gfg' : 34, 'is' : 8, 'best' : 10},
             {'gfg' : 1, 'for' : 10, 'geeks' : 9, 'and' : 5, 'best' : 12},
             {'geeks' : 8, 'find' : 3, 'gfg' : 3, 'best' : 8}]

# printing original list
print("The original list is : " + str(test_list))

res = dict()
for sub in test_list:
    for key, val in sub.items():
        if key in res:

            # combining each key to all values in
            # all dictionaries
            res[key].append(val)
        else:
            res[key] = [val]

for key, num_l in res.items():
    res[key] = mean(num_l)

# printing result
print("The Extracted average : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': 34，' is': 8，' best': 10}，{'gfg': 1，' for': 10，' geeks': 9，' and': 5，' best': 12}，{'geeks': 8，' find': 3，' gfg': 3，' best': 8}]
> 
> 提取的平均值:{'gfg': 12.66666666666666，' is': 8，' best': 10，' for': 10，' geeks': 8.5 '和':5，' find': 3}

**方法 2:使用**[**default dict()**](https://www.geeksforgeeks.org/defaultdict-in-python/)**+mean()**

在这种情况下，记忆任务是使用 defaultdict()完成的。这减少了一个条件检查，并使代码更加简洁。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Cumulative Keys Mean in Dictionary List
# Using defaultdict() + mean()
from statistics import mean
from collections import defaultdict

# initializing list
test_list = [{'gfg' : 34, 'is' : 8, 'best' : 10},
             {'gfg' : 1, 'for' : 10, 'geeks' : 9, 'and' : 5, 'best' : 12},
             {'geeks' : 8, 'find' : 3, 'gfg' : 3, 'best' : 8}]

# printing original list
print("The original list is : " + str(test_list))

# defaultdict reduces step to memoize.
res = defaultdict(list)
for sub in test_list:
    for key, val in sub.items():
        res[key].append(val)

res = dict(res)
for key, num_l in res.items():

    # computing mean
    res[key] = mean(num_l)

# printing result
print("The Extracted average : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': 34，' is': 8，' best': 10}，{'gfg': 1，' for': 10，' geeks': 9，' and': 5，' best': 12}，{'geeks': 8，' find': 3，' gfg': 3，' best': 8}]
> 
> 提取的平均值:{'gfg': 12.66666666666666，' is': 8，' best': 10，' for': 10，' geeks': 8.5 '和':5，' find': 3}