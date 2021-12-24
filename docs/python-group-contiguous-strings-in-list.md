# Python–在列表中分组连续字符串

> 原文:[https://www . geesforgeks . org/python-group-continuous-strings-in-list/](https://www.geeksforgeeks.org/python-group-contiguous-strings-in-list/)

给定一个混合列表，任务是编写一个 python 程序来分组所有连续的字符串。

```py
Input : test_list = [5, 6, 'g', 'f', 'g', 6, 5, 'i', 's', 8, 'be', 'st', 9]
Output : [5, 6, ['g', 'f', 'g'], 6, 5, ['i', 's'], 8, ['be', 'st'], 9]
Explanation : Strings are grouped to form result.

Input : test_list = [5, 6, 6, 5, 'i', 's', 8, 'be', 'st', 9]
Output : [5, 6, 6, 5, ['i', 's'], 8, ['be', 'st'], 9]
Explanation : Strings are grouped to form result.
```

**方法:使用**[**is instance()**](https://www.geeksforgeeks.org/python-isinstance-method/)**+**[**发电机**](https://www.geeksforgeeks.org/generators-in-python/)**+**[**group by()**](https://www.geeksforgeeks.org/itertools-groupby-in-python/)

在本例中，我们使用 *isinstance()* 和 *str 执行字符串识别任务，groupby()* 用于使用 *isinstance()* 对通过 key 找到的所有字符串进行分组。生成器构建列表的方式有助于将中间结果转换为列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Group contiguous strings in List
# Using isinstance() + generator + groupby()
from itertools import groupby

# checking string instance
def str_check(ele):
    return isinstance(ele, str)

def group_strs(test_list):

    # grouping list by cont. strings
    for key, grp in groupby(test_list, key=str_check):
        if key:
            yield list(grp)
        else:
            yield from grp

# initializing list
test_list = [5, 6, 'g', 'f', 'g', 6, 5,
             'i', 's', 8, 'be', 'st', 9]

# printing original list
print("The original list is : " + str(test_list))

# calling recursion fnc.
res = [*group_strs(test_list)]

# printing result
print("List after grouping : " + str(res))
```

**输出:**

> 原列表为:[5，6，' g '，' f '，' g '，6，5，' I '，' s '，8，' be '，' st '，9]
> 
> 分组后的列表:[5，6，['g '，' f '，' g']，6，5，['i '，' s']，8，['be '，' st']，9]