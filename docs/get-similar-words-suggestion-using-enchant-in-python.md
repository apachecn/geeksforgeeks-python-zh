# 使用 Python 中的附魔获得类似词语建议

> 原文:[https://www . geesforgeks . org/get-相似词-建议-使用-python 中的附魔/](https://www.geeksforgeeks.org/get-similar-words-suggestion-using-enchant-in-python/)

对于给定的用户输入，通过附魔模块得到相似的词。

`Enchant` 是 python 中的一个模块，用于检查单词的拼写，给出纠正单词的建议。同时，给出了单词的反义词和同义词。它检查字典中是否有一个单词。也可以添加其他字典，如((“en_UK”)、(“en_CA”)、(“en_GB”)等。

要安装附魔:

```py
pip install pyenchant
```

**示例:**

```py
Input : Helo
Output : Hello, Help, Hero, Helot, Hole

Input : Trth
Output : Truth, Trash, Troth, Trench

```

下面是实现:

```py
# Python program to print the similar
# words using Enchant module

# Importing the Enchant module
import enchant

# Using 'en_US' dictionary
d = enchant.Dict("en_US")

# Taking input from user
word = input("Enter word: ")

d.check(word)

# Will suggest similar words
# form given dictionary
print(d.suggest(word))
```

**输出:**

```py
Enter word: aple

['pale', 'ale', 'ape', 'maple', 'ample', 'apple', 'plea', 'able', 'apse']

```