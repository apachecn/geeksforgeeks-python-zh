# Python–跨列表的不相交字符串

> 原文:[https://www . geesforgeks . org/python-不相交-字符串-跨列表/](https://www.geeksforgeeks.org/python-disjoint-strings-across-lists/)

给定两个列表，提取所有不相交的字符串对，即没有任何共同的字符。

> **输入**:test _ list 1 =[“Hari tha”、“is”、“best”]，test _ list 2 =[“she”、“loves”、“木瓜”]
> **输出**:【(‘Hari tha’、‘loves’)、(‘is’、‘木瓜’)、(‘best’、‘木瓜’)】
> **解释**:“is”和“木瓜”没有共同的性格。
> 
> **输入** : test_list1 = [aa，cab]，test _ list 2 =[“a”、“c”]
> **输出** : []
> **解释**:无对不相交字符串。

**处理方法:利用** [**设定()**](https://www.geeksforgeeks.org/python-set-method/) **+** [**产量**](https://www.geeksforgeeks.org/python-yield-keyword/) **【发电机】+** [**减少()**](https://www.geeksforgeeks.org/reduce-in-python/)**+**[T21】递归](https://www.geeksforgeeks.org/recursion/)

在本文中，我们使用 set & operation 执行获取不相交字符串的任务，并使用 yield 动态提取。使用递归检查每个后续字符串是否不相交。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Disjoint Strings across Lists
# Using set() + yield [ generator ] + reduce() + recursion
from functools import reduce

# helper function
def dis_pairs(dpair, res=[]):

    # checking for disjoint pair
    if not dpair and not reduce(lambda a, b: set(a) & set(b), res):
        yield tuple(res)

    # recurring for subsequent pairs
    elif dpair:
        yield from [idx for k in dpair[0] for idx in dis_pairs(dpair[1:], res + [k])]

# initializing lists
test_list1 = ["haritha", "is", "best"]
test_list2 = ["she", "loves", "papaya"]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# calling function
res = list(dis_pairs([test_list1, test_list2]))

# printing result
print("All possible Disjoint pairs : " + str(res))
```

**输出:**

> 原列表 1 为:['haritha '，' is '，' best']
> 原列表 2 为:['she '，' loves '，'木瓜']
> 所有可能的不相交对:[('haritha '，' loves ')，(' is '，'木瓜')，(' best '，'木瓜')]