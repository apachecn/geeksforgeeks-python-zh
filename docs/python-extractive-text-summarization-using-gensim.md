# Python |使用 Gensim

进行文本摘要提取

> 原文:[https://www . geesforgeks . org/python-extract-text-summary-use-gensim/](https://www.geeksforgeeks.org/python-extractive-text-summarization-using-gensim/)

**摘要**是各种文本应用的有用工具，旨在突出大型语料库中的重要信息。随着网络上信息的大量涌现，Python 提供了一些方便的工具来帮助总结文本。这篇[文章](https://www.geeksforgeeks.org/ml-text-summarization-of-links-based-on-user-query/)概述了所遵循的两大类方法——提取法和抽象法。在本文中，我们将查看一个工作示例**摘要**。

**算法:**
下图是在 gensim 库中实现的算法，名为**【TextRank】**，基于 **PageRank 算法**对搜索结果进行排名。

1.  预处理给定的文本。这包括停止词删除、标点符号删除和词干。
2.  用句子做一个图，句子是顶点。
3.  该图的边表示两个句子在顶点处的相似性。
4.  在这个加权图上运行 PageRank 算法。
5.  挑选得分最高的顶点并将其附加到摘要中。
6.  根据比率或字数，决定要拾取的顶点数。

**代码:根据(a)比例和(b)字数总结一篇维基百科文章。**

## 计算机编程语言

```py
from gensim.summarization.summarizer import summarize
from gensim.summarization import keywords
import wikipedia
import en_core_web_sm

# Get wiki content.
wikisearch = wikipedia.page("Amitabh Bachchan")
wikicontent = wikisearch.content
nlp = en_core_web_sm.load()
doc = nlp(wikicontent)

# Save the wiki content to a file
# (for reference).
f = open("wikicontent.txt", "w")
f.write(wikicontent)
f.close()

# Summary (0.5% of the original content).
summ_per = summarize(wikicontent, ratio = 0.05)
print("Percent summary")
print(summ_per)

# Summary (200 words)
summ_words = summarize(wikicontent, word_count = 200)
print("Word count summary")
print(summ_words)
```

**输出**T2】

```py
Percent summary
Amitabh Bachchan (pronounced [?m??ta?b? ?b?t???n]; born Inquilaab Srivastava;
11 October 1942) is an Indian film actor, film producer, television host, 
occasional playback singer and former politician. He first gained popularity
in the early 1970s for films such as Zanjeer, Deewaar and Sholay, and was
dubbed India's "angry young man" for his on-screen roles in Bollywood.
.
.
.
Apart from National Film Awards, Filmfare Awards and other competitive awards
which Bachchan won for his performances throughout the years, he has been 
awarded several honours for his achievements in the Indian film industry.
```

```py
Word count summary
Beyond the Indian subcontinent, he also has a large overseas following 
in markets including Africa (such as South Africa), the Middle East 
(especially Egypt), United Kingdom, Russia and parts of the United 
States. Bachchan has won numerous accolades in his career, including 
four National Film Awards as Best Actor and many awards at 
international film festivals and award ceremonies.
.
.
.
After a three year stint in politics from 1984 to 1987, Bachchan 
returned to films in 1988, playing the title role in Shahenshah, 
which was a box office success.
```