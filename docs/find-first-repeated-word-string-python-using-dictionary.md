# 使用字典

在 Python 中查找字符串中的第一个重复单词

> 原文:[https://www . geesforgeks . org/find-first-repeated-word-string-python-use-dictionary/](https://www.geeksforgeeks.org/find-first-repeated-word-string-python-using-dictionary/)

**先决条件:** [字典](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/)数据结构

给定一个字符串，找到字符串中第一个重复的单词。
示例:

```py
Input : "Ravi had been saying that he had been there"
Output : had

Input : "Ravi had been saying that"
Output : No Repetition

Input : "he had had he"
Output : he

```

这个问题我们已经有了解决方案，请参考[找到一个字符串](https://www.geeksforgeeks.org/find-first-repeated-word-string/)链接中的第一个重复单词。我们可以使用[字典](https://www.youtube.com/watch?v=z7z_e5-l2yE&t=31s)数据结构在 python 中快速解决这个问题。方法很简单，

1.  给定字符串的第一个拆分由空格分隔。
2.  现在使用[集合将单词列表转换成字典。计数器(迭代器)](https://www.geeksforgeeks.org/counters-in-python-set-1/)方法。字典以单词为关键字，以频率为值。
3.  现在再次遍历单词列表，检查第一个单词的频率是否大于 1。

```py
# Function to Find the first repeated word in a string 
from collections import Counter 

def firstRepeat(input): 

    # first split given string separated by space 
    # into words 
    words = input.split(' ') 

    # now convert list of words into dictionary 
    dict = Counter(words) 

    # traverse list of words and check which first word 
    # has frequency > 1 
    for key in words: 
        if dict[key]>1: 
            print (key) 
            return

# Driver program 
if __name__ == "__main__": 
    input = 'Ravi had been saying that he had been there'
    firstRepeat(input) 
```

输出:

```py
had

```