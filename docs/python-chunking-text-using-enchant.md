# Python–使用附魔对文本进行分块

> 原文:[https://www . geesforgeks . org/python-chunking-text-use-附魔/](https://www.geeksforgeeks.org/python-chunking-text-using-enchant/)

`Enchant`是 Python 中的一个模块，用于检查单词的拼写，给出纠正单词的建议。同时，给出了单词的反义词和同义词。它检查字典中是否有一个单词。

`Enchant`还提供了 **`enchant.tokenize`** 模块对文本进行标记化。标记化包括从正文中拆分单词。但有时并不是所有的单词都需要进行标记。假设我们有一个 HTML 文件，在标记化时，所有的标签也将被包括在内。通常，HTML 标签对文章的内容没有贡献，因此有必要将它们排除在外。

目前唯一实现的 chunker 是 HTMLChunker。一个用于 LaTeX 文档的分块器正在开发中。

```
# import the required modules
from enchant.tokenize import get_tokenizer
from enchant.tokenize import HTMLChunker

# the text to be tokenized
text = "<div> <h1> Geeks for Geeks </h1> <br> </div>"

# getting tokenizer class
tokenizer = get_tokenizer("en_US")

# printing tokens without chunking
print("Printing tokens without chunking:")
token_list = []
for words in tokenizer(text):
    token_list.append(words)
print(token_list)

# getting tokenizer class with chunk
tokenizer_chunk = get_tokenizer("en_US", chunkers = (HTMLChunker, ))

# printing tokens after chunking
print("\nPrinting tokens after chunking:")
token_list_chunk = []
for words in tokenizer_chunk(text):
    token_list_chunk.append(words)
print(token_list_chunk)
```

**输出:**

> 不分块打印令牌:
> [('div '，1)、(' h '，7)、(' Geeks '，11)、(' for '，17)、(' Geeks '，21)、(' h '，29)、(' br '，34)、(' div '，40)]
> 
> 分块后打印代币:
> [(极客，11)、(' for '，17)、('极客，21)]