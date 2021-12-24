# Python–从文本中提取标签

> 原文:[https://www . geesforgeks . org/python-extract-hashtags-from-text/](https://www.geeksforgeeks.org/python-extract-hashtags-from-text/)

一个**哈希表**是一个关键字或短语，前面有一个哈希符号(#)，写在帖子或评论中以突出显示它并方便搜索。一些例子是:#like，#gfg，#自拍
我们得到了一个包含标签的字符串，我们必须将这些标签提取到一个列表中并打印出来。

**示例:**

```py
Input : GeeksforGeeks is a wonderful #website for #ComputerScience
Output :  website , ComputerScience

Input : This day is beautiful! #instagood #photooftheday #cute
Output :  instagood, photooftheday, cute
```

**方法 1:**

*   使用 Split()方法将文本拆分成单词。
*   对于每个单词，检查第一个字符是否是哈希符号(#)。
*   如果是，则将该单词添加到没有哈希符号的哈希表列表中。
*   打印标签列表。

## 蟒蛇 3

```py
# function to print all the hashtags in a text
def extract_hashtags(text):

    # initializing hashtag_list variable
    hashtag_list = []

    # splitting the text into words
    for word in text.split():

        # checking the first character of every word
        if word[0] == '#':

            # adding the word to the hashtag_list
            hashtag_list.append(word[1:])

    # printing the hashtag_list
    print("The hashtags in \"" + text + "\" are :")
    for hashtag in hashtag_list:
        print(hashtag)

if __name__=="__main__":
    text1 = "GeeksforGeeks is a wonderful # website for # ComputerScience"
    text2 = "This day is beautiful ! # instagood # photooftheday # cute"
    extract_hashtags(text1)
    extract_hashtags(text2)
```

**输出:**

```py
The hashtags in "GeeksforGeeks is a wonderful #website for #ComputerScience" are :
website
ComputerScience
The hashtags in "This day is beautiful! #instagood #photooftheday #cute" are :
instagood
photooftheday
cute
```

**方法二:**使用正则表达式。

## 蟒蛇 3

```py
# import the regex module
import re

# function to print all the hashtags in a text
def extract_hashtags(text):

    # the regular expression
    regex = "#(\w+)"

    # extracting the hashtags
    hashtag_list = re.findall(regex, text)

    # printing the hashtag_list
    print("The hashtags in \"" + text + "\" are :")
    for hashtag in hashtag_list:
        print(hashtag)

if __name__=="__main__":
    text1 = "GeeksforGeeks is a wonderful # website for # ComputerScience"
    text2 = "This day is beautiful ! # instagood # photooftheday # cute"
    extract_hashtags(text1)
    extract_hashtags(text2)
```

**输出:**

```py
The hashtags in "GeeksforGeeks is a wonderful #website for #ComputerScience" are :
website
ComputerScience
The hashtags in "This day is beautiful! #instagood #photooftheday #cute" are :
instagood
photooftheday
cute
```