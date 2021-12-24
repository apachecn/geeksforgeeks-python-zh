# Python |查找给定列表中 k 个最长的单词

> 原文:[https://www . geesforgeks . org/python-find-k-给定列表中最长的单词/](https://www.geeksforgeeks.org/python-find-k-longest-words-in-given-list/)

给定一个单词列表和一个正整数 K，编写一个 Python 程序，按照长度降序在列表中查找 K 个最长的单词。

**示例:**

```
Input : lst  = ['am', 'watermelon', 'girl', 'boy', 'colour'], K = 3
Output : ['watermelon', 'colour', 'girl']

Input : ['see', 'I', 'geek', 'on', 'brain'], K = 4
Output : ['brain', 'geek', 'see', 'on']

```

**方法#1 :** 使用 *itertools* 中的 *count()*

首先，根据单词的长度对“lst”进行排序，然后根据计数器变量进行排序，以便后面出现的单词获得更高的优先级，从而提取 k 个变量。

```
# Python3 program to Find 
# longest K words in a list
from itertools import count

def longest_word(lst, K):
    cnt = count()
    return sorted(lst, key = lambda w : (len(w), next(cnt)), 
                                        reverse = True)[:K]

# Driver code
lst = ['am', 'watermelon', 'girl', 'boy', 'colour']
K = 3
print(longest_word(lst, K))
```

**Output:**

```
['watermelon', 'colour', 'girl']

```

**方法 2 :** 使用*排序()*

```
# Python3 program to Find 
# longest K words in a list

def longest_word(lst, K):
    idx, words = zip(*sorted(enumerate(lst), 
    key = lambda w: (-len(w[1]), -w[0]))[:K])
    return list(words)

# Driver code
lst = ['am', 'watermelon', 'girl', 'boy', 'colour']
K = 3
print(longest_word(lst, K))
```

**Output:**

```
['watermelon', 'colour', 'girl']

```

**方法三:**使用*堆*

```
# Python3 program to Find 
# longest K words in a list
import heapq
from operator import itemgetter

def longest_word(lst, K):
    # constructing heap
    heap = [(0, i, '') for i in range(K)]
    heapq.heapify(heap)

    # To maintain top K elements
    for i, word in enumerate(lst):
        item = (len(word), i, word)
        if item > heap[0]:
            heapq.heapreplace(heap, item)

    return sorted(list(map(itemgetter(2), heap)),
                            key = len, reverse = True)

# Driver code
lst = ['am', 'watermelon', 'girl', 'boy', 'colour']
K = 3
print(longest_word(lst, K))
```

**Output:**

```
['watermelon', 'colour', 'girl']

```