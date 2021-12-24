# 如何用 Python 构建随机故事生成器？

> 原文:[https://www . geesforgeks . org/如何使用 python 构建随机故事生成器/](https://www.geeksforgeeks.org/how-to-build-a-random-story-generator-using-python/)

在本节中，我们将制作一个非常有趣的 Python 初级项目。这是一个随机的故事发生器。随机故事生成器项目旨在每次用户执行代码时生成随机故事。一个故事由一系列句子组成。我们将随机选择短语来构建句子，从而构建故事。

现在，相关的问题是——我们将如何做？它的答案很简单:

*   First, we put the elements of the story in different lists.
*   Then we will use the random module to select random parts of stories collected in different lists.
*   Then connect them together to make a story.

我们将使用 random.choice()函数。在开始之前，让我们看看 random.choice()的工作原理。

## 蟒蛇 3

```py
import random

# list of books is stored in the list -'books'
books = ['Mother', 'Midnight Children', 'My experiments with truth']

# An item from the list 'books' is selected
# by random.choice()
print(random.choice(books))
```

**Output**

```py
Midnight Children
```

我们可以看到， [random.choice()](https://www.geeksforgeeks.org/python-numbers-choice-function/) 函数基本上是从项目列表中选择一个项目。

以下是随机故事生成器项目中涉及的步骤。

**1。**导入随机模块，因为它是 python 的内置模块。所以，不需要手动安装。

## 蟒 3

```py
# Importing random module
import random
```

**2。**定义几个短语列表。这里，我们定义了八个列表。我们还可以定义更多，这完全取决于我们的选择。

*   At the beginning of the sentence-this list gives the time when the event happened.
*   People-This list tells the protagonist of this story.
*   Time–This list defines the exact date when an event occurred.
*   Story _ plot-–This list defines the plot of the story.
*   Location–This list defines the location where the event occurred.
*   Second _ character-–this list defines the second character of the story.
*   Age–This list defines the age of the second character.
*   Work-This list tells what the second role is doing.

## 蟒 3

```py
# Defining list of phrases which will help to build a story
Sentence_starter = ['About 100 years ago', ' In the 20 BC', 'Once upon a time']

character = [' there lived a king.',' there was a man named Jack.',
             ' there lived a farmer.']

time = [' One day', ' One full-moon night']

story_plot = [' he was passing by', ' he was going for a picnic to ']

place = [' the mountains', ' the garden']

second_character = [' he saw a man', ' he saw a young lady']

age = [' who seemed to be in late 20s', ' who seemed very old and feeble']

work = [' searching something.', ' digging a well on roadside.']
```

3.在 random.choice()的帮助下，从每个列表中选择一个项目，并连接所选项目以生成故事的句子。

## 蟒 3

```py
# Selecting an item from each list and concatenating them.
print(random.choice(Sentence_starter)+random.choice(character)+
      random.choice(time)+random.choice(story_plot)+
      random.choice(place)+random.choice(second_character)+
      random.choice(age)+random.choice(work))
```

**实施:**

让我们借助一个例子来尝试一下完整的实现。

T2T4

```py
# Importing random module
import random

# Defining list of phrases which will help to build a story

Sentence_starter = ['About 100 years ago', ' In the 20 BC', 'Once upon a time']
character = [' there lived a king.',' there was a man named Jack.',
             ' there lived a farmer.']
time = [' One day', ' One full-moon night']
story_plot = [' he was passing by',' he was going for a picnic to ']
place = [' the mountains', ' the garden']
second_character = [' he saw a man', ' he saw a young lady']
age = [' who seemed to be in late 20s', ' who seemed very old and feeble']
work = [' searching something.', ' digging a well on roadside.']

# Selecting an item from each list and concatenating them.
print(random.choice(Sentence_starter)+random.choice(character)+
      random.choice(time)+random.choice(story_plot) +
      random.choice(place)+random.choice(second_character)+
      random.choice(age)+random.choice(work))
```

T5

**输出:**

> 公元前 20 年有一个国王。一天，他去山上野餐，看到一个看起来 20 多岁的男人在路边挖井。

这样，我们可以任意多次编译和运行这段代码。并且会产生不同的短篇小说。