# Python–根据单词创建首字母缩略词

> 原文:[https://www . geesforgeks . org/python-create-缩略语-from-word/](https://www.geeksforgeeks.org/python-create-acronyms-from-words/)

给定一个字符串，任务是编写一个 Python 程序从该字符串中提取首字母缩略词。

**示例:**

> **输入:**计算机科学工程
> 
> **输出:** CSE
> 
> **输入:**极客为极客
> 
> **输出:** GFG
> 
> **输入:**北方邦
> 
> **输出:**上升

**方法 1:**

需要以下步骤:

*   将输入作为字符串。
*   将字符串的第一个字母添加到输出中。
*   迭代整个字符串，并将下一个字母添加到要输出的空格中。
*   将输出更改为大写(必需的首字母缩略词)。

## 蟒蛇 3

```py
# function to create acronym
def fxn(stng):

    # add first letter
    oupt = stng[0]

    # iterate over string
    for i in range(1, len(stng)):
        if stng[i-1] == ' ':

            # add letter next to space
            oupt += stng[i]

    # uppercase oupt
    oupt = oupt.upper()
    return oupt

# input string
inpt1 = "Computer Science Engineering"

# output acronym
print(fxn(inpt1))

# input string
inpt1 = "geeks for geeks"

# output acronym
print(fxn(inpt1))

# input string
inpt1 = "Uttar pradesh"

# output acronym
print(fxn(inpt1))
```

**输出:**

```py
CSE
GFG
UP
```

**方法 2:**

需要以下步骤:

*   将输入作为字符串。
*   把单词分开。
*   迭代单词，并将第一个字母添加到输出中。
*   将输出更改为大写(必需的首字母缩略词)。

## 蟒蛇 3

```py
# function to create acronym
def fxn(stng):

    # get all words
    lst = stng.split()
    oupt = ""

    # iterate over words
    for word in lst:

        # get first letter of each word
        oupt += word[0]

    # uppercase oupt
    oupt = oupt.upper()
    return oupt

# input string
inpt1 = "Computer Science Engineering"

# output acronym
print(fxn(inpt1))

# input string
inpt1 = "geeks for geeks"

# output acronym
print(fxn(inpt1))

# input string
inpt1 = "Uttar pradesh"

# output acronym
print(fxn(inpt1))
```

**输出:**

```py
CSE
GFG
UP
```