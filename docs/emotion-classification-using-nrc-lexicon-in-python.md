# 使用 Python 中的 NRC 词典进行情感分类

> 原文:[https://www . geesforgeks . org/情感-分类-使用-NRC-词典-in-python/](https://www.geeksforgeeks.org/emotion-classification-using-nrc-lexicon-in-python/)

很多时候，对于现实世界的项目，情绪识别往往只是项目的开始。在上面编写完整的代码不仅会增加时间，而且效率也会受到阻碍。

*NRCLexicon* 是麻省理工学院批准的 *pypi* 项目，由马克·m·贝利设计，预测给定文本的情绪和情感。该软件包包含大约 27，000 个单词，基于加拿大国家研究委员会(NRC)的情感词典和 *NLTK* 图书馆的 *WordNet* 同义词集。

### **安装:**

要安装此模块，请在终端中键入以下命令。

```py
pip install NRCLex
```

即使安装了该模块，运行程序时也可能出现 *MissingCorpusError* 。所以建议在命令提示符下使用下面的命令安装*textblob . download _ corpora*。

```py
python -m textblob.download_corpora
```

**进场:**

*   导入模块

## 蟒蛇 3

```py
# Import required modules
from nrclex import NRCLex
```

*   分配输入文本

## 蟒蛇 3

```py
# Assigning list of words
text = ['hate', 'lovely', 'person', 'worst']
```

*   为每个输入文本创建 *NRCLex* 对象。

## 蟒蛇 3

```py
for i in range(len(text)):

    # creating objects
    emotion = NRCLex(text[i])
```

*   运用方法对情绪进行分类。

<figure class="table">

| Sr | 方法 | 描述 |
| --- | --- | --- |
| one | *情感词汇* | 返回单词列表。 |
| Two | *情感句子* | 返回句子列表。 |
| three | *情感.情感 _ 列表* | 返回影响列表。 |
| four | *情感.情感 _ 字典* | 返回影响字典。 |
| five | *情感. raw_emotion_scores* | 返回原始情感计数。 |
| six | *情绪. top_emotions* | 回报最高的情感。 |
| seven | *情绪影响频率* | 返回影响频率。 |

</figure>

*   测量的情绪影响包括以下内容:

1.  害怕
2.  愤怒
3.  希望
4.  信任
5.  惊喜
6.  积极的
7.  否定的；消极的；负面的；负的
8.  悲哀
9.  厌恶
10.  高兴

下面是实现。

**例 1:**

基于上述方法，下面的示例使用 *top_emotions 对各种情绪进行分类。*

## 蟒蛇 3

```py
# Import module
from nrclex import NRCLex

# Assign list of strings
text = ['hate', 'lovely', 'person', 'worst']

# Iterate through list
for i in range(len(text)):

    # Create object
    emotion = NRCLex(text[i])

    # Classify emotion
    print('\n\n', text[i], ': ', emotion.top_emotions)
```