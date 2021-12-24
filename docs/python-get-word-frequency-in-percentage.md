# Python–获取词频百分比

> 原文:[https://www . geesforgeks . org/python-get-word-frequency-in-percent/](https://www.geeksforgeeks.org/python-get-word-frequency-in-percentage/)

给定一个字符串列表，任务是编写一个 Python 程序来获取字符串列表中每个单词的百分比份额。

**计算解释:**(X 字出现次数/总字数)* 100。

**示例:**

> **输入:**test _ list =[“Gfg 最适合极客”、“All love Gfg”、“Gfg 最适合 CS”、“对于 CS 极客，Gfg 最好”]
> 
> **输出:** {'Gfg': 0.21052631578947367，' is': 0.15789473684210525，' best': 0.15789473684210525，' for': 0.10526315789473684，' geeks': 0.10526315789473684，' All': 0。
> 
> **解释:**每个单词 wrt 的频率百分比。计算列表中的所有其他单词。Gfg 出现 4 次。总字数= 19。
> 
> **输入:**test _ list =[“Gfg 最适合极客”，“大家都爱 Gfg”]
> 
> **输出:**{“Gfg”:0.25，“is”:0.125，“best”:0.125，“for”:0.125，“极客”:0.125，“All”:0.125，“love”:0.125 }
> 
> **解释:**每个单词 wrt 的频率百分比。计算列表中的所有其他单词。

**方法#1:使用**[**sum()**](https://www.geeksforgeeks.org/sum-function-python/)**+**[**Counter()**](https://www.geeksforgeeks.org/counters-in-python-set-2-accessing-counters/)**+**[**join()**](https://www.geeksforgeeks.org/join-function-python/)**+**[T21】split()](https://www.geeksforgeeks.org/python-string-split/)

在本例中，我们在使用 join()连接每个字符串后，使用 split()执行获取每个单词的任务。Counter()获取每个单词映射的频率。发布使用 sum()计算的所有单词大小可以获得每个单词所需的份额，利用存储在 Counter 中的频率。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Each word frequency percentage
# Using sum() + Counter()+ join() + split()
from collections import Counter

# initializing list
test_list = ["Gfg is best for geeks",
             "All love Gfg", 
             "Gfg is best for CS",
             "For CS geeks Gfg is best"]

# printing original list
print("The original list is : " + str(test_list))

# concatenating using join 
joined = " ".join(ele for ele in test_list)

# mapping using Counter()
mappd = Counter(joined.split())

# getting total using sum 
total_val = sum(mappd.values())

# getting share of each word
res = {key: val / total_val for key,
       val in mappd.items()}

# printing result
print("Percentage share of each word : " + str(res))
```

**输出:**

> 原列表为:['Gfg 最适合极客'，' All love Gfg '，' Gfg 最适合 CS '，'对于 CS 极客，Gfg 最好']
> 
> 每个单词所占的百分比份额:{'Gfg': 0.21052631578947367，' is': 0.15789473684210525，' best': 0.15789473684210525，' for': 0.10526315789473684，'极客':0.105263157894，' All ':0.0505050504794

**方法 2:使用组合单线**

与上述方法类似，只是将每个片段组合起来，以提供紧凑的单个线性解决方案。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Each word frequency percentage
# Using combined one-liner 
from collections import Counter

# initializing list
test_list = ["Gfg is best for geeks", "All love Gfg", 
            "Gfg is best for CS", "For CS geeks Gfg is best"]

# printing original list
print("The original list is : " + str(test_list))

# mapping using Counter()
mappd = Counter(" ".join(ele for ele in test_list).split())

# getting share of each word
res = {key: val / sum(mappd.values()) for key,
       val in mappd.items()}

# printing result
print("Percentage share of each word : " + str(res))
```

**输出:**

> 原列表为:['Gfg 最适合极客'，' All love Gfg '，' Gfg 最适合 CS '，'对于 CS 极客，Gfg 最好']
> 
> 每个单词所占的百分比份额:{'Gfg': 0.21052631578947367，' is': 0.15789473684210525，' best': 0.15789473684210525，' for': 0.10526315789473684，'极客':0.105263157894，' All ':0.0505050504794