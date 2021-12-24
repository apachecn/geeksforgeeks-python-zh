# 使用更好的脏话审查 Python 中的脏话

> 原文:[https://www . geesforgeks . org/御史-python 中的坏词-使用更好的脏话/](https://www.geeksforgeeks.org/censor-bad-words-in-python-using-better-profanity/)

在本文中，我们将学习如何使用 Python 审查不良单词。为此，我们使用 python 中的**better _ professional**模块。

**安装**

```py
pip install better_profanity
```

对于审查脏话，我们使用的是来自 better _ professional的 professional . review()方法。所以，我们先讨论它的语法和参数。

> **语法:**亵渎。审查(文本，审查 _char='* '
> 
> **参数:**
> 
> **文本:**待审查文本
> 
> **御史 _char :** '* '默认情况下，字符要御史不良文字
> 
> **返回值:**审查文本

**进场:**

1.  导入包(脏话)
2.  声明或输入要审查的文本。
3.  使用亵渎。审查()方法，获得审查的文本。
4.  打印经过审查的文本。

**例 1:**

## 蟒蛇 3

```py
# importing package
from better_profanity import profanity

# text to be censored
text = "What the shit are you doing?"

# do censoring
censored = profanity.censor(text)

# view output
print(censored)
```

**输出:**

```py
What the **** are you doing?
```

**例 2:**

## 蟒蛇 3

```py
# importing package
from better_profanity import profanity

# text to be censored
text = "What the shit are you doing?"

# do censoring
censored = profanity.censor(text, '{content}apos;)

# view output
print(censored)
```

**输出:**

```py
What the $$ are you doing?
```