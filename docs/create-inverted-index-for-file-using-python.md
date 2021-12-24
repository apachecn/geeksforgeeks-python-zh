# 使用 Python 为文件创建倒排索引

> 原文:[https://www . geesforgeks . org/create-inverted-index-for-file-use-python/](https://www.geeksforgeeks.org/create-inverted-index-for-file-using-python/)

倒排索引是一种存储从内容(如单词或数字)到其在文档或文档集中的位置的映射的索引数据结构。简而言之，它是一个类似 hashmap 的数据结构，将您从一个单词引导到一个文档或网页。

### 创建倒排索引

我们将创建一个**单词级倒排索引**，也就是说它将返回单词所在的行的列表。我们还将创建一个字典，其中键值表示文件中存在的单词，字典的值将由包含它们所在的行号的列表来表示。要在木星笔记本中创建文件，使用魔法功能:

```py
%%writefile file.txt
This is the first word.
This is the second text, Hello! How are you?
This is the third, this is it now.

```

这将创建一个名为 file.txt 的文件，它将包含以下内容。

#### **读取文件:**

## 蟒蛇 3

```py
# this will open the file
file = open('file.txt', encoding='utf8')
read = file.read()
file.seek(0)
read

# to obtain the
# number of lines
# in file
line = 1
for word in read:
    if word == '\n':
        line += 1
print("Number of lines in file is: ", line)

# create a list to
# store each line as
# an element of list
array = []
for i in range(line):
    array.append(file.readline())

array
```

**输出:**

```py
Number of lines in file is: 3
['This is the first word.\n',
'This is the second text, Hello! How are you?\n',
'This is the third, this is it now.']

```

**使用的功能:**

*   **打开:**用于打开文件。
*   **读取:**此功能用于读取文件内容。
*   **seek(0):** 它将光标返回到文件的开头。

#### **去掉标点符号:**

## 蟒蛇 3

```py
punc = '''!()-[]{};:'"\, <>./?@#$%^&*_~'''
for ele in read:  
    if ele in punc:  
        read = read.replace(ele, " ")  

read

# to maintain uniformity
read=read.lower()                    
read
```

**输出:**

```py
'this is the first word \n
this is the second text hello how are you \n
this is the third this is it now '

```

#### **通过删除停止字来清除数据:**

停止词是那些没有与之相关联的情感，并且可以在不牺牲句子意义的情况下被安全忽略的词。

## 蟒蛇 3

```py
from nltk.tokenize import word_tokenize
import nltk
from nltk.corpus import stopwords
nltk.download('stopwords')

for i in range(1):
    # this will convert
    # the word into tokens
    text_tokens = word_tokenize(read)

tokens_without_sw = [
    word for word in text_tokens if not word in stopwords.words()]

print(tokens_without_sw)
```

**输出:**

```py
['first', 'word', 'second', 'text', 'hello', 'third']

```

#### **创建**一个**倒排索引:**T4】

## 蟒蛇 3

```py
dict = {}

for i in range(line):
    check = array[i].lower()
    for item in tokens_without_sw:

        if item in check:
            if item not in dict:
                dict[item] = []

            if item in dict:
                dict[item].append(i+1)

dict
```

**输出:**

```py
{'first': [1],
'word': [1],
'second': [2], 
'text': [2], 
'hello': [2], 
'third': [3]}

```