# Python |从列表中查找输入字符串的所有相近匹配项

> 原文:[https://www . geesforgeks . org/python-find-close-matches-input-string-list/](https://www.geeksforgeeks.org/python-find-close-matches-input-string-list/)

我们得到了一个模式字符串列表和一个输入字符串。我们需要在模式字符串列表中找到所有可能的足够好的输入字符串匹配。

示例:

```
Input : patterns = ['ape', 'apple', 
                  'peach', 'puppy'], 
          input = 'appel'
Output : ['apple', 'ape']

```

我们可以使用内置函数**difflib . get _ close _ matches()**在 python 中快速解决这个问题。

### difflib.get_close_matches()函数在 Python 中是如何工作的？

**difflib.get_close_matches(单词，可能性，n，截止)**接受四个参数，其中 **n，截止**可选。**单词**是期望紧密匹配的序列，**可能性**是匹配单词的序列列表。可选参数 **n(默认为 3)** 是要返回的最大相近匹配数，n 必须大于 0。可选参数**截止值(默认为 0.6)** 是[0，1]范围内的一个浮点数。得分至少和单词不太相似的可能性被忽略。
可能性中的最佳(不超过 n 个)匹配在列表中返回，按相似性得分排序，最相似的优先。

```
# Function to find all close matches of 
# input string in given list of possible strings
from difflib import get_close_matches

def closeMatches(patterns, word):
     print(get_close_matches(word, patterns))

# Driver program
if __name__ == "__main__":
    word = 'appel'
    patterns = ['ape', 'apple', 'peach', 'puppy']
    closeMatches(patterns, word)
```

**<u>参考文献:</u>**[https://docs.python.org/2/library/difflib.html](https://docs.python.org/2/library/difflib.html)

输出:

```
['apple', 'ape']

```