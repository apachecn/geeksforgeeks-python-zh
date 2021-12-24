# Python–组相似的开始和结束字符单词

> 原文:[https://www . geesforgeks . org/python-group-similar-start-and-end-character-words/](https://www.geeksforgeeks.org/python-group-similar-start-and-end-character-words/)

有时，在处理 Python 数据时，我们可能会遇到这样的问题，即我们需要根据前端和后端字符对所有单词进行分组。这种应用程序在我们处理数据的领域很常见，比如 web 开发。让我们讨论执行这项任务的某些方法。

**方法#1:使用`defaultdict()` +循环**
上述功能的组合可用于执行该任务。在这种情况下，我们使用字符串切片符号检查前面和最后一个元素，并存储在 dict 中。以第一个和最后一个字符作为关键字。

```
# Python3 code to demonstrate working of 
# Group Similar Start and End character words
# Using defaultdict() + loop
from collections import defaultdict

def end_check(word):
    sub1 = word.strip()[0]
    sub2 = word.strip()[-1]
    temp = sub1 + sub2
    return temp

def front_check(word):
    sub = word.strip()[1:-1]
    return sub

# initializing string
test_str = 'geeksforgeeks is indias best and bright for geeks'

# printing original string
print("The original string is : " + str(test_str))

# Group Similar Start and End character words
# Using defaultdict() + loop
test_list = test_str.split()
res = defaultdict(set)
for ele in test_list:
    res[end_check(ele)].add(front_check(ele))

# printing result 
print("The grouped dictionary is : " + str(dict(res))) 
```

**Output :**

> 原字符串为:geeksforgeeks 是印度最棒最亮眼的极客
> 分组字典为:{'fr': {'o'}，' bt': {'righ '，' es'}，' ad': {'n'}，' GS ':{ ' eeksforgek '，' eek'}，' is ' { "，' ndia'}}