# Python–百分比范围内的元素频率

> 原文:[https://www . geesforgeks . org/python-元素-频率-百分比范围/](https://www.geeksforgeeks.org/python-element-frequencies-in-percent-range/)

给定一个元素列表和百分比范围，任务是编写一个 python 程序来提取频率在给定范围内的所有元素。

> **输入:** test_list = [4，6，2，4，6，7，8，4，9，1，4，6，7，8]，strt，end = 13，25
> 
> **输出:**【6，7，8】
> 
> **说明:** 21.4、14.2、14.2 分别是 6、7、8 的百分比存在。
> 
> **输入:** test_list = [4，6，2，4，6，7，8，4，9，1，4，6，7，8]，strt，end = 13，20
> 
> **输出:**【7，8】
> 
> **说明:** 14.2、14.2 分别是 7、8 的百分比存在。

存在感百分比可以通过以下公式简单计算:

```
Frequency of the element present in the list/ total no. of elements in the list
```

**方法#1:使用** [**计数器()**](https://www.geeksforgeeks.org/counters-in-python-set-1/) **+** [**设置()**](https://www.geeksforgeeks.org/python-sets/) **+** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)**+**[T21】len()](https://www.geeksforgeeks.org/python-string-length-len/)

在这种情况下，使用循环提取所有元素的频率。下一步是获取列表的元素集，并检查频率是否在指定的范围内。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Element frequencies in percent range
# Using Counter() + set() + loop + len()
from collections import Counter

# initializing list
test_list = [4, 6, 2, 4, 6, 7, 8, 4, 9, 1, 4, 6, 7, 8]

# printing original list
print("The original list is : " + str(test_list))

# initializing percent ranges
strt, end = 13, 25

# getting frequencies
freqs = dict(Counter(test_list))

# computing percents and assigning
res = []
for ele in set(test_list):
    percent = (freqs[ele] / len(test_list)) * 100
    if percent >= strt and percent <= end:
        res.append(ele)

# printing result
print("Elements within range of frequencies : " + str(res))
```

**输出:**

```
The original list is : [4, 6, 2, 4, 6, 7, 8, 4, 9, 1, 4, 6, 7, 8]
Elements within range of frequencies : [6, 7, 8]
```

**方法 2:使用**[**Counter()**](https://www.geeksforgeeks.org/counters-in-python-set-1/)**+**[**循环**](https://www.geeksforgeeks.org/loops-in-python/)**+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)
这以几乎相似的方式执行任务，关键区别在于 Counter 键是迭代的，而不是列表元素，因为它们会提供相似的输出。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Element frequencies in percent range
# Using Counter() + loop + len()
from collections import Counter

# initializing list
test_list = [4, 6, 2, 4, 6, 7, 8, 4, 9, 1, 4, 6, 7, 8]

# printing original list
print("The original list is : " + str(test_list))

# initializing percent ranges
strt, end = 13, 25

# getting frequencies
freqs = dict(Counter(test_list))

# computing percents and assigning
# iterating from dictionary
res = []
for ele in freqs:
    percent = (freqs[ele] / len(test_list)) * 100
    if percent >= strt and percent <= end:
        res.append(ele)

# printing result
print("Elements within range of frequencies : " + str(res))
```

**输出:**

```
The original list is : [4, 6, 2, 4, 6, 7, 8, 4, 9, 1, 4, 6, 7, 8]
Elements within range of frequencies : [6, 7, 8]
```