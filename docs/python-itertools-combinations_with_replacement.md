# Python–ITER tools。组合 _ 带 _ 替换()

> 原文:[https://www . geeksforgeeks . org/python-ITER tools-combinations _ with _ replacement/](https://www.geeksforgeeks.org/python-itertools-combinations_with_replacement/)

[Python 中的 Itertools](https://www.geeksforgeeks.org/python-itertools/) 是指 Python 中提供的用于创建迭代器的模块，这有助于提高循环效率、时间和空间效率。Itertools 帮助我们轻松高效地解决复杂问题。迭代器一般有三种类型。
**本模块提供的不同类型的迭代器有:**

*   [组合发电机](https://www.geeksforgeeks.org/python-itertools/#combine)

*   [无限迭代器](https://www.geeksforgeeks.org/python-itertools/#infinite)

*   [终止迭代器](https://www.geeksforgeeks.org/python-itertools/#terminate)

**注:**更多信息请参考[Python Itertools](https://www.geeksforgeeks.org/python-itertools/)T4】

## Itertools 组合 _ 带 _ 替换()

ItertoolsCombinations_with_replacement()位于 itertools 的组合生成器子类型中。组合生成器指的是那些处理迭代器可能的不同排列的迭代器。这里的元素是用索引值引用的，而不是用值或类型引用的。
**如何使用 Itertools。Combinations_with_replacement()函数？**
顾名思义，“组合”是指迭代器的所有可能的子集或排列，单词“combinations_with_replacement”是指允许元素在子集内重复的所有可能的排列或子集。该函数将“r”作为输入，这里“r”代表可能的不同组合的大小。所有重复元素的组合都被发出，长度为“r”，这里“r”是一个必要的参数。
**例 1:-**

## 蟒蛇 3

```py
from itertools import combinations_with_replacement

a ="GEeks"

l = list(combinations_with_replacement(a, 2))
print("COMBINATIONS WITH REPLACEMENTS OF STRING GEeks OF SIZE 2.")
print(l)
```

**输出:-**

> 替换 2 号字符串极客的组合。
> 【(' G '，' G ')，(' G '，' E ')，(' G '，' k ')，(' G '，' s ')，(' E '，' E ')，(' E '，' E '，' k ')，(' E '，' s ')，(' E '，' E '，' k ')，(' k '，' s ')，(' k '，' s '，(' s '，' s')]

**例 2:-**

## 蟒蛇 3

```py
from itertools import combinations_with_replacement

print ("All the combination of List in sorted order(with replacement) is:")  
print(list(combinations_with_replacement('D.P.S.', 2)))  
print()  

print ("All the combination of list in sorted order(with replacement) is:")  
print(list(combinations_with_replacement(range(1, 5), 2)))
```

**输出:-**

> 所有按排序顺序排列的 List 组合(不替换)为:
> [('D '，' D ')，(' D '，'.')，(' D '，' P '，(' D '，'.')，(' D '，' S ')，(' D '，'.'), ('.', '.'), ('.'，' P '，('.', '.'), ('.'，' S ')，('.', '.')，(' P '，' P ')，(' P '，')，(' P '，' S '，(' P '，'.'), ('.', '.'), ('.'，' S ')，('.', '.')，(' S '，' S ')，(' S '，'.'), ('.', '.')]
> 所有列表的组合按排序顺序(带替换)为:
> [(1，1)，(1，2)，(1，3)，(1，4)，(2，2)，(2，3)，(2，4)，(3，3)，(3，4)，(4，4)]