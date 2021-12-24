# Python |在文本文件中查找“n”个字符单词

> 原文:[https://www . geesforgeks . org/python-find-n-character-word-in-a-text-file/](https://www.geeksforgeeks.org/python-finding-n-character-words-in-a-text-file/)

本文旨在寻找具有一定数量字符的单词。在下面提到的代码中，给出了一个 python 程序来查找文本文件中包含三个字符的单词。

**示例:**

> **输入:**您好，您好吗？
> 
> **输出:**T2
> 你好
> 吗

**代码:Python 程序查找文字文件中包含三个字符的单词**

```py
count = 1
chrw = ""

# text file
file = open('textfile.txt', 'r')
while 1:
    sp = file.read(1)

    if count<= 3:
        chrw = chrw + sp

    if count>3:
        if sp ==" ":
            count = 0
            if len(chrw)>0:
                print(chrw)
                chrw =""
        elif sp !=" ":
            chrw =""
    count = count + 1

    if not sp:
        break

file.close() 
```

**输出:**

```py
how 
are 
you 
```