# Python |给定列表中的组字谜

> 原文:[https://www . geesforgeks . org/python-group-anagrams-from-given-list/](https://www.geeksforgeeks.org/python-group-anagrams-from-given-list/)

字谜是由相似的元素组成的单词，但是这些字符出现的顺序不同。有时，我们可能会遇到一个问题，我们需要将字谜分组，因此解决上述问题总是有帮助的。让我们讨论一下实现这一点的某些方法。
**方法#1:使用 default dict()+sorted()+values()**
以上函数的组合可以得到上述问题的解。在这种情况下，我们首先使用 defaultdict 对字谜进行分组，并使用 sorted 函数获取每个字谜根值来对字谜进行分组。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Grouping Anagrams
# using defaultdict() + sorted() + values()
from collections import defaultdict

# initializing list
test_list = ['lump', 'eat',  'me',  'tea', 'em', 'plum']

# printing original list
print("The original list : " + str(test_list))

# using defaultdict() + sorted() + values()
# Grouping Anagrams
temp = defaultdict(list)
for ele in test_list:
    temp[str(sorted(ele))].append(ele)
res = list(temp.values())

# print result
print("The grouped Anagrams : " + str(res))
```

**Output : **

```py
The original list : ['lump', 'eat', 'me', 'tea', 'em', 'plum']
The grouped Anagrams : [['me', 'em'], ['lump', 'plum'], ['eat', 'tea']]

```

**方法 2:使用列表理解+排序()+ lambda + groupby()**
以上功能的组合也可以用来执行这个特定的任务。groupby 函数一起执行必要的分组。lambda 函数有助于对相似的字谜进行分组。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Grouping Anagrams
# using list comprehension + sorted() + lambda + groupby()
from itertools import groupby

# initializing list
test_list = ['lump', 'eat',  'me',  'tea', 'em', 'plum']

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + sorted() + lambda + groupby()
# Grouping Anagrams
temp = lambda test_list: sorted(test_list)
res = [list(val) for key, val in groupby(sorted(test_list, key = temp), temp)]

# print result
print("The grouped Anagrams : " + str(res))
```

**Output : **

```py
The original list : ['lump', 'eat', 'me', 'tea', 'em', 'plum']
The grouped Anagrams : [['me', 'em'], ['lump', 'plum'], ['eat', 'tea']]

```

**方法 3:使用简单的 Python 编程**

下面是用简单的 python 编程方式将字谜单词组合在一起的程序。不使用列表理解或 lambda 或导入的方法。

遵循的方法很简单–

1.对每个单词进行排序，并将排序后的单词用作词典关键字

2.根据排序后的关键字不断向词典中添加新单词

## 蟒蛇 3

```py
data = ['eat', 'ate', 'tea', 'ant', 'tan',
        'bat', 'adobe', 'abode', 'listen', 'silent']

def createAnagramKey(string):
    key = ''
    for ch in sorted(string):
        key += ch
    return str(key)

def groupAnagramWords(data):
    group = dict()
    for ele in data:
        if group.get(createAnagramKey(ele)) == None:
            group[createAnagramKey(ele)] = [ele]
        else:
            group[createAnagramKey(ele)].append(ele)
    return group

anagram_grouped = groupAnagramWords(data)

# Anagram in dictonry format
print('In dictonry format')
print(anagram_grouped)

anagram_grouped_list = list()

for k, v in anagram_grouped.items():
    anagram_grouped_list.append(v)
print('In list format')
print(anagram_grouped_list)
```

**输出:**

```py
In dictonry format
{'aet': ['eat', 'ate', 'tea'], 'ant': ['ant', 'tan'], 'abt': ['bat'],
 'abdeo': ['adobe', 'abode'], 'eilnst': ['listen', 'silent']}

In list format
[['eat', 'ate', 'tea'], ['ant', 'tan'], ['bat'], ['adobe', 'abode'], ['listen', 'silent']]
```