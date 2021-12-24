# Python |检查给定的单词是否一起出现在句子列表中

> 原文:[https://www . geesforgeks . org/python-检查给定单词是否出现在句子列表中/](https://www.geeksforgeeks.org/python-check-if-given-words-appear-together-in-a-list-of-sentence/)

给定一个句子“句子”列表和一个单词“单词”列表，编写一个 Python 程序来查找句子列表中的哪个句子由“单词”中包含的所有单词组成，并在列表中返回它们。

**示例:**

```py
Input : sentence = ['I love tea', 'He hates tea', 'We love tea']
        words = ['love', 'tea']
Output : ['I love tea', 'We love tea']

Input : sentence = ['python coder', 'geeksforgeeks', 'coder in geeksforgeeks']
        words = ['coder', 'geeksforgeeks']
Output : ['coder in geeksforgeeks']

```

**方法#1 :** 使用列表理解

我们首先使用列表理解，为句子列表的每个子串返回一个布尔值，并将其存储在“res”中。最后，根据“res”中的布尔值返回包含所需句子的列表。

```py
# Python3 program to Check if given words 
# appear together in a list of sentence

def check(sentence, words):
    res = [all([k in s for k in words]) for s in sentence]
    return [sentence[i] for i in range(0, len(res)) if res[i]]

# Driver code
sentence = ['python coder', 'geeksforgeeks', 'coder in geeksforgeeks']
words = ['coder', 'geeksforgeeks']
print(check(sentence, words))
```

**Output:**

```py
['coder in geeksforgeeks']

```

**方法 2 :** 列表理解(替代方法)

对于句子列表中的每个子串，它检查当前子串中有多少单词，并将其存储在变量“k”中。如果“k”的长度与单词列表的长度匹配，只需将其附加到“res”中。

```py
# Python3 program to Check if given words 
# appear together in a list of sentence

def check(sentence, words):
    res = []
    for substring in sentence:
        k = [ w for w in words if w in substring ]
        if (len(k) == len(words) ):
            res.append(substring)

    return res

# Driver code
sentence = ['python coder', 'geeksforgeeks', 'coder in geeksforgeeks']
words = ['coder', 'geeksforgeeks']
print(check(sentence, words))
```

**Output:**

```py
['coder in geeksforgeeks']

```

**进场#3 :** 巨蟒`map()`

`map()`方法对句子列表应用一个函数，并通过拆分单词列表来检查列表中是否包含所有单词。它为句子列表的每个子串返回一个布尔值，并将其存储在“res”中。最后，重复与方法#1 相同的步骤。

```py
# Python3 program to Check if given words 
# appear together in a list of sentence

def check(sentence, words):
    res = list(map(lambda x: all(map(lambda y:y in x.split(),
                                          words)), sentence))
    return [sentence[i] for i in range(0, len(res)) if res[i]]

# Driver code
sentence = ['python coder', 'geeksforgeeks', 'coder in geeksforgeeks']
words = ['coder', 'geeksforgeeks']
print(check(sentence, words))
```

**Output:**

```py
['coder in geeksforgeeks']

```