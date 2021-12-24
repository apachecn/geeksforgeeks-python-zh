# 如何使用 Python 获取给定单词所在的行号？

> 原文:[https://www . geesforgeks . org/如何使用 python 获得给定单词所在的行号/](https://www.geeksforgeeks.org/how-to-obtain-the-line-number-in-which-given-word-is-present-using-python/)

要从给定单词所在的文件中获取行号，请创建一个列表，其中每个索引都包含每行的内容。为此，请遵循以下说明。

首先，我们需要一个文件来读取。因此，使用如下所示的神奇功能在木星笔记本内创建一个文件:

```
%%writefile geeks.txt 
Hello, I am Romy 
I am a content writer at GfG 
Nice to meet you 
Hello, hii all fine
```

或者你可以使用任何*。txt 文件。*

## 蟒 3

```
# READ FILE
df = open("geeks.txt")

# read file
read = df.read()

# return cursor to
# the beginning
# of the file.
df.seek(0)
read
```