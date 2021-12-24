# 模糊不清的 Python 库

> 原文:[https://www.geeksforgeeks.org/fuzzywuzzy-python-library/](https://www.geeksforgeeks.org/fuzzywuzzy-python-library/)

python 中有很多比较字符串的方法。一些主要方法有:

1.  使用正则表达式
2.  简单比较
3.  使用 difflib

但是其中一个非常简单的方法是使用**模糊不清的**库，在这里我们可以得到 100 分的分数，这表示两个字符串通过给出相似性指数是相等的。本文讨论我们如何开始使用模糊的库。

FuzzyWuzzy 是一个 Python 库，用于字符串匹配。模糊字符串匹配是查找与给定模式匹配的字符串的过程。基本上它使用 [Levenshtein Distance](https://en.wikipedia.org/wiki/Levenshtein_distance) 来计算序列之间的差异。
[FuzzyWuzzy](https://github.com/seatgeek/fuzzywuzzy) 由 SeatGeek 开发和开源，SeatGeek 是一个寻找体育和音乐会门票的服务。他们最初的用例，在他们的[博客中讨论过。](http://chairnerd.seatgeek.com/fuzzywuzzy-fuzzy-string-matching-in-python/)

**Requirements of fuzzywuzzy**
*   Python 2.4 或更高版本
*   python-莱文斯坦

**通过 pip 安装:**

```
pip install fuzzywuzzy
pip install python-Levenshtein

```

**如何使用这个库？**

首先导入这些模块，

```
from fuzzywuzzy import fuzz
from fuzzywuzzy import process
```

简单比率用法:

```
fuzz.ratio('geeksforgeeks', 'geeksgeeks')
87

# Exact match
fuzz.ratio('GeeksforGeeks', 'GeeksforGeeks')  

100
fuzz.ratio('geeks for geeks', 'Geeks For Geeks ') 
80
```

```
fuzz.partial_ratio("geeks for geeks", "geeks for geeks!")
100
# Exclamation mark in second string, 
but still partially words are same so score comes 100

fuzz.partial_ratio("geeks for geeks", "geeks geeks")
64
# score is less because there is a extra 
token in the middle middle of the string.
```

现在，令牌集比率和令牌排序比率:

```
# Token Sort Ratio
fuzz.token_sort_ratio("geeks for geeks", "for geeks geeks")
100

# This gives 100 as every word is same, irrespective of the position 

# Token Set Ratio
fuzz.token_sort_ratio("geeks for geeks", "geeks for for geeks")
88
 fuzz.token_set_ratio("geeks for geeks", "geeks for for geeks")
100
# Score comes 100 in second case because token_set_ratio 
considers duplicate words as a single word.
```

现在假设我们有一个选项列表，我们想要找到最接近的匹配，我们可以使用**处理**模块

```
query = 'geeks for geeks'
choices = ['geek for geek', 'geek geek', 'g. for geeks'] 

# Get a list of matches ordered by score, default limit to 5
process.extract(query, choices)
[('geeks geeks', 95), ('g. for geeks', 95), ('geek for geek', 93)]

# If we want only the top one
process.extractOne(query, choices)
('geeks geeks', 95)
```

还有一个常用的比率叫做 **WRatio** ，有时候用 WRatio 代替简单的比率会更好，因为 WRatio 也处理上下限和其他一些参数。

```
fuzz.WRatio('geeks for geeks', 'Geeks For Geeks')
100
fuzz.WRatio('geeks for geeks!!!','geeks for geeks')
100
# whereas simple ratio will give for above case
fuzz.ratio('geeks for geeks!!!','geeks for geeks')
91
```

**全代码**

```
# Python code showing all the ratios together, 
# make sure you have installed fuzzywuzzy module

from fuzzywuzzy import fuzz
from fuzzywuzzy import process

s1 = "I love GeeksforGeeks"
s2 = "I am loving GeeksforGeeks"
print "FuzzyWuzzy Ratio: ", fuzz.ratio(s1, s2)
print "FuzzyWuzzy PartialRatio: ", fuzz.partial_ratio(s1, s2)
print "FuzzyWuzzy TokenSortRatio: ", fuzz.token_sort_ratio(s1, s2)
print "FuzzyWuzzy TokenSetRatio: ", fuzz.token_set_ratio(s1, s2)
print "FuzzyWuzzy WRatio: ", fuzz.WRatio(s1, s2),'\n\n'

# for process library,
query = 'geeks for geeks'
choices = ['geek for geek', 'geek geek', 'g. for geeks'] 
print "List of ratios: "
print process.extract(query, choices), '\n'
print "Best among the above list: ",process.extractOne(query, choices)
```

输出:

```
FuzzyWuzzy Ratio:  84
FuzzyWuzzy PartialRatio:  85
FuzzyWuzzy TokenSortRatio:  84
FuzzyWuzzy TokenSetRatio:  86
FuzzyWuzzy WRatio:  84 

List of ratios: 
[('g. for geeks', 95), ('geek for geek', 93), ('geek geek', 86)] 

Best among the above list:  ('g. for geeks', 95)

```

FuzzyWuzzy 库建立在 difflib 库之上，python-Levenshtein 用于速度。所以这是 python 中字符串匹配的最佳方式之一。