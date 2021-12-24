# Python |在列表中分组相似子串

> 原文:[https://www . geesforgeks . org/python-分组-相似-列表中的子字符串/](https://www.geeksforgeeks.org/python-grouping-similar-substrings-in-list/)

有时，我们有一个应用程序，其中我们要求将公共前缀字符串分组为一个，以便可以根据分组进行进一步的处理。这种类型的分组在机器学习和网络开发的情况下非常有用。让我们讨论一下实现这一点的某些方法。
**方法一:使用 lambda+ITER tools . group by()+split()**
以上三个功能的组合帮助我们完成任务。拆分方法很关键，因为它定义了必须执行分组的分隔符。groupby 函数对元素进行分组。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# group similar substrings
# using lambda + itertools.groupby() + split()
from itertools import groupby

# initializing list
test_list = ['geek_1', 'coder_2', 'geek_4', 'coder_3', 'pro_3']

# sort list
# essential for grouping
test_list.sort()

# printing the original list
print ("The original list is : " + str(test_list))

# using lambda + itertools.groupby() + split()
# group similar substrings
res = [list(i) for j, i in groupby(test_list,
                  lambda a: a.split('_')[0])]

# printing result
print ("The grouped list is : " + str(res))
```

**Output : **

原列表为:['coder_2 '，' coder_3 '，' geek_1 '，' geek_4 '，' pro_3']
分组列表为:['coder_2 '，' coder_3']，['geek_1 '，' geek_4']，['pro_3']]

**方法 2:使用 lambda+ITER tools . group by()+partition()**
也可以通过用 partition 函数替换 split 函数来执行类似的任务。这是执行这个任务更有效的方法，因为它使用迭代器，因此在内部更快。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# group similar substrings
# using lambda + itertools.groupby() + partition()
from itertools import groupby

# initializing list
test_list = ['geek_1', 'coder_2', 'geek_4', 'coder_3', 'pro_3']

# sort list
# essential for grouping
test_list.sort()

# printing the original list
print ("The original list is : " + str(test_list))

# using lambda + itertools.groupby() + partition()
# group similar substrings
res = [list(i) for j, i in groupby(test_list,
              lambda a: a.partition('_')[0])]

# printing result
print ("The grouped list is : " + str(res))
```

**Output : **

原列表为:['coder_2 '，' coder_3 '，' geek_1 '，' geek_4 '，' pro_3']
分组列表为:['coder_2 '，' coder_3']，['geek_1 '，' geek_4']，['pro_3']]