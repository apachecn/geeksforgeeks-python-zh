# Python |统计给定文本文件中每个单词的出现次数(使用字典)

> 原文:[https://www . geesforgeks . org/python-给定文本文件中每个单词的出现次数-使用字典/](https://www.geeksforgeeks.org/python-count-occurrences-of-each-word-in-given-text-file-using-dictionary/)

很多时候需要计算文本文件中每个单词的出现次数。为了实现这一点，我们使用了一个字典对象，它将单词存储为关键字，将其计数存储为相应的值。我们遍历文件中的每个单词，并将其添加到字典中，计数为 1。如果这个词已经存在于字典中，我们就把它的计数增加 1。

**示例#1:**
首先我们创建一个文本文件，我们要对其进行字数统计。假设该文件为`**sample.txt**` ，内容如下:

```py
Mango banana apple pear
Banana grapes strawberry
Apple pear mango banana
Kiwi apple mango strawberry

```

**注意:**确保文本文件和 Python 文件在同一个目录下。

```py
# Open the file in read mode
text = open("sample.txt", "r")

# Create an empty dictionary
d = dict()

# Loop through each line of the file
for line in text:
    # Remove the leading spaces and newline character
    line = line.strip()

    # Convert the characters in line to 
    # lowercase to avoid case mismatch
    line = line.lower()

    # Split the line into words
    words = line.split(" ")

    # Iterate over each word in line
    for word in words:
        # Check if the word is already in dictionary
        if word in d:
            # Increment count of word by 1
            d[word] = d[word] + 1
        else:
            # Add the word to dictionary with count 1
            d[word] = 1

# Print the contents of dictionary
for key in list(d.keys()):
    print(key, ":", d[key])
```

**输出:**

```py
mango : 3
banana : 3
apple : 3
pear : 2
grapes : 1
strawberry : 2
kiwi : 1

```

**例 2:**

考虑一个有带标点符号的句子的文件`**sample.txt**`。

```py
Mango! banana apple pear.
Banana, grapes strawberry.
Apple- pear mango banana.
Kiwi "apple" mango strawberry.

```

```py
import string

# Open the file in read mode
text = open("sample.txt", "r")

# Create an empty dictionary
d = dict()

# Loop through each line of the file
for line in text:
    # Remove the leading spaces and newline character
    line = line.strip()

    # Convert the characters in line to 
    # lowercase to avoid case mismatch
    line = line.lower()

    # Remove the punctuation marks from the line
    line = line.translate(line.maketrans("", "", string.punctuation))

    # Split the line into words
    words = line.split(" ")

    # Iterate over each word in line
    for word in words:
        # Check if the word is already in dictionary
        if word in d:
            # Increment count of word by 1
            d[word] = d[word] + 1
        else:
            # Add the word to dictionary with count 1
            d[word] = 1

# Print the contents of dictionary
for key in list(d.keys()):
    print(key, ":", d[key])
```

**输出:**

```py
mango : 3
banana : 3
apple : 3
pear : 2
grapes : 1
strawberry : 2
kiwi : 1

```