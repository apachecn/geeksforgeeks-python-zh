# 一款 Python 字谜游戏

> 原文:[https://www.geeksforgeeks.org/project-idea-game-anagrams/](https://www.geeksforgeeks.org/project-idea-game-anagrams/)

**项目想法:**
这个项目的目的是用 python 创建一个游戏，在这个游戏中，用户被呈现一个单词的字谜，并且必须在有限的尝试次数内猜出正确的单词。

**项目特点:**

1.  用户被给予固定次数的猜测正确单词的尝试。尝试的次数取决于单词的长度。
2.  在每一次不正确的尝试之后，都会向用户提供正确单词的提示。
3.  如果用户在固定的尝试次数内不能猜出正确的单词，则显示正确的单词，游戏继续下一个单词。
4.  Ctrl+C 或 Ctrl+D 退出游戏。

**实现:**
本教程仅对基于 Linux 的系统有效。本教程是在 Linux Mint 17.1 系统上编写的。关于在其他 Linux 系统(红帽、Arch)上的实现，请参见本教程末尾的特别说明。

在几乎所有基于 Linux 的系统中，都有一个位于目录位置“/usr/share/dict/”的文件，它有不同的名称，如“CRA lib-small”(基于 Ubuntu 的系统)、“words”(Redhat，Arch)，其中包含字典中的单词，许多应用程序经常使用它来实现“拼写检查”等功能。

在这个项目中，我将使用相同的文件来创建一个字谜游戏。

阅读文件可以为我们提供游戏所需的所有单词。文件中的单词用新的一行分隔，因此在读取文件时，我们需要根据新的一行字符拆分单词，以获得单个单词。相同的代码如下所示:

## 蟒蛇 3

```py
loc='/usr/share/dict/cracklib-small'
with open(loc) as f:
content=f.read().split('\n')
f.close()
```

该文件还包含像“动物园的”这样的词，但我们不希望这样的词出现在我们的游戏中，所以我们可以省略它们。为了避免让游戏变得太简单，我决定也省略长度小于 5 的单词，但是这一步是可选的，可以跳过。相同的代码如下所示:

## 蟒蛇 3

```py
l=len(content)
words=[]
for i in range(0,l):
    if '\'' in content[i] or len(content[i])<5:
    continue
words.append(content[i])
```

该文件的开头还包含类似“第二，第三”的单词。为了防止它们出现在我们的游戏中，我们省略了它们:

## 蟒蛇 3

```py
words=words[1:]
d=len(words)
words=words[:d]
```