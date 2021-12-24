# Python–使用附魔过滤文本

> 原文:[https://www . geesforgeks . org/python-过滤-文本-使用-附魔/](https://www.geeksforgeeks.org/python-filtering-text-using-enchant/)

`Enchant`是 Python 中的一个模块，用于检查单词的拼写，给出纠正单词的建议。同时，给出了单词的反义词和同义词。它检查字典中是否有一个单词。

`Enchant`还提供了 **`enchant.tokenize`** 模块对文本进行标记化。标记化包括从正文中拆分单词。但有时并不是所有的单词都需要进行标记。假设我们正在进行拼写检查，那么通常会忽略电子邮件地址和网址。这可以通过使用过滤器修改令牌化过程来实现。
目前实施的过滤器有:

*   电子邮件过滤器
*   URL filter(URL 过滤)
*   WikiWordFilter

**示例 1 :** 电子邮件过滤器

```py
# import the required modules
from enchant.tokenize import get_tokenizer
from enchant.tokenize import EmailFilter

# the text to be tokenized
text = "The email is abc@gmail.com"

# getting tokenizer class
tokenizer = get_tokenizer("en_US")

# printing tokens without filtering
print("Printing tokens without filtering:")
token_list = []
for words in tokenizer(text):
    token_list.append(words)
print(token_list)

# getting tokenizer class with filter
tokenizer_filter = get_tokenizer("en_US", [EmailFilter])

# printing tokens after filtering
print("\nPrinting tokens after filtering:")
token_list_filter = []
for words in tokenizer_filter(text):
    token_list_filter.append(words)
print(token_list_filter)
```

**输出:**

> 不过滤打印令牌:
> [('The '，0)、(' email '，4)、(' is '，10)、(' abc '，13)、(' gmail '，17)、(' com '，23)]
> 
> 过滤后打印令牌:
> [('The '，0)、(' email '，4)、(' is '，10)

**示例 2 :** URLFilter

```py
# import the required modules
from enchant.tokenize import get_tokenizer
from enchant.tokenize import URLFilter

# the text to be tokenized
text = "This is an URL: https://www.geeksforgeeks.org/"

# getting tokenizer class
tokenizer = get_tokenizer("en_US")

# printing tokens without filtering
print("Printing tokens without filtering:")
token_list = []
for words in tokenizer(text):
    token_list.append(words)
print(token_list)

# getting tokenizer class with filter
tokenizer_filter = get_tokenizer("en_US", [URLFilter])

# printing tokens after filtering
print("\nPrinting tokens after filtering:")
token_list_filter = []
for words in tokenizer_filter(text):
    token_list_filter.append(words)
print(token_list_filter)
```

**输出:**

> 不过滤打印令牌:
> [('This '，0)、(' is '，5)、(' an '，8)、(' URL '，11)、(' https '，16)、(' www '，24)、(' geeksforgeeks '，28)、(' org '，42)]
> 
> 过滤后打印令牌:
> [('This '，0)、(' is '，5)、(' an '，8)、(' URL '，11)]

**例 3:**WikiWord filter
WikiWord 是由两个或两个以上以大写字母开头的单词组成的单词，一起运行。

```py
# import the required modules
from enchant.tokenize import get_tokenizer
from enchant.tokenize import WikiWordFilter

# the text to be tokenized
text = "VersionFiveDotThree is an example of WikiWord"

# getting tokenizer class
tokenizer = get_tokenizer("en_US")

# printing tokens without filtering
print("Printing tokens without filtering:")
token_list = []
for words in tokenizer(text):
    token_list.append(words)
print(token_list)

# getting tokenizer class with filter
tokenizer_filter = get_tokenizer("en_US", [WikiWordFilter])

# printing tokens after filtering
print("\nPrinting tokens after filtering:")
token_list_filter = []
for words in tokenizer_filter(text):
    token_list_filter.append(words)
print(token_list_filter)
```

**输出:**

> 在不过滤的情况下打印令牌:
> [(' versionivedotthree '，0)、(' is '，20)、(' an '，23)、(' example '，26)、(' of '，34)、(' WikiWord '，37)]
> 
> 过滤后打印令牌:
> [('is '，20)、(' an '，23)、(' example '，26)、(' of '，34)]