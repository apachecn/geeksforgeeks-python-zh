# Python–带示例的引理方法

> 原文:[https://www . geeksforgeeks . org/python-引理-方法-示例/](https://www.geeksforgeeks.org/python-lemmatization-approaches-with-examples/)

下面是探索 python 中各种引理化方法的分步指南，以及一些示例和代码实现。强烈建议您坚持给定的流程，除非您对主题有所了解，在这种情况下，您可以查阅下面给出的任何方法。

![](img/3d31e6a05f21cd33632a8551a020e95d.png)

**什么是引理化？**
与[词干](https://www.geeksforgeeks.org/python-stemming-words-with-nltk/)相比，引理化要强大得多。它超越了单词简化，考虑到一种语言的全部词汇，对单词应用**形态分析**，旨在仅移除屈折词尾，并返回单词的基础或词典形式，这被称为**引理**。

为了清楚起见，请看下面给出的例子:

```py
Original Word ---> Root Word (lemma)      Feature

   meeting    --->   meet                (core-word extraction)
   was        --->    be                 (tense conversion to present tense)
   mice       --->   mouse               (plural to singular)
```

> **提示:在执行任何 NLP 任务(包括引理)之前，请始终将您的文本转换为小写。**

**引理化的各种方法:**
我们将复习 **9 种不同的方法**来执行引理化以及多个例子和代码实现。

1.  WordNet
2.  WordNet(带位置标签)
3.  TextBlob
4.  文本块(带位置标签)
5.  宽大的
6.  TreeTagger
7.  模式
8.  玄诗
9.  斯坦福 CoreNLP

**1。Wordnet Lemmatizer**
Wordnet 是一个公开的词汇数据库，包含 200 多种语言，提供单词之间的语义关系。这是最早和最常用的引理技巧之一。

*   它存在于 python 中的 **nltk 库**中。
*   Wordnet 将单词链接成语义关系。(如同义词)
*   它以**synset**的形式对同义词进行分组。
    *   **synset**:语义等价的一组数据元素。**T3】**

**如何使用:**

1.  **下载 nltk 包**:在你的水蟒提示或者终端中，键入:
    pip 安装 nltk
2.  **从 nltk** 下载 Wordnet:在你的 pyhton 控制台中，执行以下操作:
    导入 nltk
    nltk . Download(【Wordnet】)
    nltk . Download(【average _ perceptor _ tagger 】)

**代码:**

## 蟒蛇 3

```py
import nltk
nltk.download('wordnet')
from nltk.stem import WordNetLemmatizer

# Create WordNetLemmatizer object
wnl = WordNetLemmatizer()

# single word lemmatization examples
list1 = ['kites', 'babies', 'dogs', 'flying', 'smiling',
         'driving', 'died', 'tried', 'feet']
for words in list1:
    print(words + " ---> " + wnl.lemmatize(words))

#> kites ---> kite
#> babies ---> baby
#> dogs ---> dog
#> flying ---> flying
#> smiling ---> smiling
#> driving ---> driving
#> died ---> died
#> tried ---> tried
#> feet ---> foot
```

**代码:**

## 蟒蛇 3

```py
# sentence lemmatization examples
string = 'the cat is sitting with the bats on the striped mat under many flying geese'

# Converting String into tokens
list2 = nltk.word_tokenize(string)
print(list2)
#> ['the', 'cat', 'is', 'sitting', 'with', 'the', 'bats', 'on',
#   'the', 'striped', 'mat', 'under', 'many', 'flying', 'geese']

lemmatized_string = ' '.join([wnl.lemmatize(words) for words in list2])

print(lemmatized_string)  
#> the cat is sitting with the bat on the striped mat under many flying goose
```

**2。Wordnet Lemmatizer(带 POS 标签)**
在上面的方法中，我们观察到 Wordnet 的结果并不达标。“坐”、“飞”等词在引理后保持不变。这是因为这些词在给定的句子中被视为名词，而不是动词。为了克服这一点，我们使用词性标签。
我们添加一个标签，标签上有一个定义其类型的特定单词(动词、名词、形容词等)。
例如
<u>单词</u> + <u>类型(POS tag)</u> — > <u>引理化单词</u>
驾驶+动词‘v’—>驾驶
狗+名词‘n’—>狗

**代码:**

## 蟒蛇 3

```py
# WORDNET LEMMATIZER (with appropriate pos tags)

import nltk
from nltk.stem import WordNetLemmatizer
nltk.download('averaged_perceptron_tagger')
from nltk.corpus import wordnet

lemmatizer = WordNetLemmatizer()

# Define function to lemmatize each word with its POS tag

# POS_TAGGER_FUNCTION : TYPE 1
def pos_tagger(nltk_tag):
    if nltk_tag.startswith('J'):
        return wordnet.ADJ
    elif nltk_tag.startswith('V'):
        return wordnet.VERB
    elif nltk_tag.startswith('N'):
        return wordnet.NOUN
    elif nltk_tag.startswith('R'):
        return wordnet.ADV
    else:         
        return None

sentence = 'the cat is sitting with the bats on the striped mat under many badly flying geese'

# tokenize the sentence and find the POS tag for each token
pos_tagged = nltk.pos_tag(nltk.word_tokenize(sentence)) 

print(pos_tagged)
#>[('the', 'DT'), ('cat', 'NN'), ('is', 'VBZ'), ('sitting', 'VBG'), ('with', 'IN'),
# ('the', 'DT'), ('bats', 'NNS'), ('on', 'IN'), ('the', 'DT'), ('striped', 'JJ'),
# ('mat', 'NN'), ('under', 'IN'), ('many', 'JJ'), ('flying', 'VBG'), ('geese', 'JJ')]

# As you may have noticed, the above pos tags are a little confusing.

# we use our own pos_tagger function to make things simpler to understand.
wordnet_tagged = list(map(lambda x: (x[0], pos_tagger(x[1])), pos_tagged))
print(wordnet_tagged)
#>[('the', None), ('cat', 'n'), ('is', 'v'), ('sitting', 'v'), ('with', None),
# ('the', None), ('bats', 'n'), ('on', None), ('the', None), ('striped', 'a'),
# ('mat', 'n'), ('under', None), ('many', 'a'), ('flying', 'v'), ('geese', 'a')]

lemmatized_sentence = []
for word, tag in wordnet_tagged:
    if tag is None:
        # if there is no available tag, append the token as is
        lemmatized_sentence.append(word)
    else:       
        # else use the tag to lemmatize the token
        lemmatized_sentence.append(lemmatizer.lemmatize(word, tag))
lemmatized_sentence = " ".join(lemmatized_sentence)

print(lemmatized_sentence)
#> the cat can be sit with the bat on the striped mat under many fly geese
```

**3。TextBlob**
TextBlob 是一个用于处理文本数据的 python 库。它提供了一个简单的应用编程接口来访问它的方法和执行基本的自然语言处理任务。

**下载 textblob 包:**在您的蟒蛇提示或终端中，键入:
pip 安装 TextBlob

**代码:**

## 蟒蛇 3

```py
from textblob import TextBlob, Word

my_word = 'cats'

# create a Word object
w = Word(my_word)

print(w.lemmatize())
#> cat

sentence = 'the bats saw the cats with stripes hanging upside down by their feet.'

s = TextBlob(sentence)
lemmatized_sentence = " ".join([w.lemmatize() for w in s.words])

print(lemmatized_sentence)
#> the bat saw the cat with stripe hanging upside down by their foot
```

**4。TextBlob(带有 POS 标签)**
与 Wordnet 方法相同，没有使用适当的 POS 标签，我们也观察到了该方法的相同限制。因此，我们使用文本块模块的一个更强大的方面——“词性”标记来克服这个问题。

**代码:**

## 蟒蛇 3

```py
from textblob import TextBlob

# Define function to lemmatize each word with its POS tag

# POS_TAGGER_FUNCTION : TYPE 2
def pos_tagger(sentence):
    sent = TextBlob(sentence)
    tag_dict = {"J": 'a', "N": 'n', "V": 'v', "R": 'r'}
    words_tags = [(w, tag_dict.get(pos[0], 'n')) for w, pos in sent.tags]   
    lemma_list = [wd.lemmatize(tag) for wd, tag in words_tags]
    return lemma_list

# Lemmatize
sentence = "the bats saw the cats with stripes hanging upside down by their feet"
lemma_list = pos_tagger(sentence)
lemmatized_sentence = " ".join(lemma_list)
print(lemmatized_sentence)
#> the bat saw the cat with stripe hang upside down by their foot

lemmatized_sentence = " ".join([w.lemmatize() for w in t_blob.words])
print(lemmatized_sentence)
#> the bat saw the cat with stripe hanging upside down by their foot
```

> 以下是所有类型的[标签缩写](https://www.geeksforgeeks.org/python-part-of-speech-tagging-using-textblob/?ref=rp)及其含义的链接。(向下滚动标签表)

**5。spaCy**
spaCy 是一个开源的 python 库，可以解析和“理解”大量的文本。针对特定语言(英语、法语、德语等)提供单独的型号。).

```py
Download spaCy package :(a) Open anaconda prompt or terminal as administrator and run the command:

            (b) Now, open anaconda prompt or terminal normally and run the command:

If successful, you should see a message like:

    Linking successful
    C:\Anaconda3\envs\spacyenv\lib\site-packages\en_core_web_sm -->
    C:\Anaconda3\envs\spacyenv\lib\site-packages\spacy\data\en

You can now load the model via 
```

**代码:**

## 蟒蛇 3

```py
import spacy
nlp = spacy.load('en_core_web_sm')

# Create a Doc object
doc = nlp(u'the bats saw the cats with best stripes hanging upside down by their feet')

# Create list of tokens from given string
tokens = []
for token in doc:
    tokens.append(token)

print(tokens)
#> [the, bats, saw, the, cats, with, best, stripes, hanging, upside, down, by, their, feet]

lemmatized_sentence = " ".join([token.lemma_ for token in doc])

print(lemmatized_sentence)
#> the bat see the cat with good stripe hang upside down by -PRON- foot
```

在上面的代码中，我们观察到这种方法比我们以前的方法更强大，因为:

*   甚至**亲名词**也被检测到。(由 **-PRON-** 确定)
*   连**最好的**都改成了**好。**

**6。TreeTagger**
TreeTagger 是一个用词性和引理信息标注文本的工具。TreeTagger 已经成功地用于标记超过 25 种语言，并且如果手动标记的训练语料库可用，它也适用于其他语言。

<figure class="table">

| 单词 | 刷卡机 | 引理 |
| --- | --- | --- |
| 这 | 暗行扫描(Dark Trace) | 这 |
| TreeTagger | 公证人 | TreeTagger |
| 是 | VBZ | 是 |
| 容易的 | 姐姐(网络用语)ˌ法官ˌ裁判员(judges) | 容易的 |
| 到 | 到 | 到 |
| 使用 | 动词 | 使用 |
| 。 | 送 | 。 |

</figure>

```py
How to use: 
1\. Download TreeTagger package : In your anaconda prompt or terminal, type:

2\. Download TreeTagger Software: Click on TreeTagger and download the software as per your OS. 
(Steps of installation given on website)
```

**代码:**

## 蟒蛇 3

```py
# 6\. TREETAGGER LEMMATIZER
import pandas as pd
import treetaggerwrapper as tt

t_tagger = tt.TreeTagger(TAGLANG ='en', TAGDIR ='C:\Windows\TreeTagger')

pos_tags = t_tagger.tag_text("the bats saw the cats with best stripes hanging upside down by their feet")

original = []
lemmas = []
tags = []
for t in pos_tags:
    original.append(t.split('\t')[0])
    tags.append(t.split('\t')[1])
    lemmas.append(t.split('\t')[-1])

Results = pd.DataFrame({'Original': original, 'Lemma': lemmas, 'Tags': tags})
print(Results)

#>      Original  Lemma Tags
# 0       the     the   DT
# 1      bats     bat  NNS
# 2       saw     see  VVD
# 3       the     the   DT
# 4      cats     cat  NNS
# 5      with    with   IN
# 6      best    good  JJS
# 7   stripes  stripe  NNS
# 8   hanging    hang  VVG
# 9    upside  upside   RB
# 10     down    down   RB
# 11       by      by   IN
# 12    their   their  PP$
# 13     feet    foot  NNS
```

**7。模式**
模式是一个 Python 包，常用于网页挖掘、自然语言处理、机器学习和网络分析。它有许多有用的 NLP 功能。它还包含一个我们将在下面讨论的特殊功能。

```py
How to use: 
Download Pattern package: In your anaconda prompt or terminal, type:

```

**代码:**

## 蟒蛇 3

```py
# PATTERN LEMMATIZER
import pattern
from pattern.en import lemma, lexeme
from pattern.en import parse

sentence = "the bats saw the cats with best stripes hanging upside down by their feet"

lemmatized_sentence = " ".join([lemma(word) for word in sentence.split()])

print(lemmatized_sentence)
#> the bat see the cat with best stripe hang upside down by their feet

# Special Feature : to get all possible lemmas for each word in the sentence
all_lemmas_for_each_word = [lexeme(wd) for wd in sentence.split()]
print(all_lemmas_for_each_word)

#> [['the', 'thes', 'thing', 'thed'],
#   ['bat', 'bats', 'batting', 'batted'],
#   ['see', 'sees', 'seeing', 'saw', 'seen'],
#   ['the', 'thes', 'thing', 'thed'],
#   ['cat', 'cats', 'catting', 'catted'],
#   ['with', 'withs', 'withing', 'withed'],
#   ['best', 'bests', 'besting', 'bested'],
#   ['stripe', 'stripes', 'striping', 'striped'],
#   ['hang', 'hangs', 'hanging', 'hung'],
#   ['upside', 'upsides', 'upsiding', 'upsided'],
#   ['down', 'downs', 'downing', 'downed'],
#   ['by', 'bies', 'bying', 'bied'],
#   ['their', 'theirs', 'theiring', 'theired'],
#   ['feet', 'feets', 'feeting', 'feeted']]
```

> **注意**:如果上面的代码出现了一个错误，说**“发电机提升停止迭代”**。再运行一次。试了 3-4 次就可以了。

**8。Gensim**
Gensim 旨在使用数据流处理大型文本集合。它的旅鼠化设施是基于我们上面安装的**模式**包。

*   **gensim.utils.lemmatize()** 函数可用于执行 Lemmatization。这个方法属于 python 中的 utils 模块。
*   我们可以从模式中使用这个引理器来提取 **UTF8 编码的标记**，它们的基本形式=引理。
*   默认只考虑**名词**、**动词**、**形容词**、**副词**(其他所有引理均弃用)。
*   例如

```py
Word          --->  Lemmatized Word 
are/is/being  --->  be
saw           --->  see
```

```py
How to use: 
1\. Download Pattern package: In your anaconda prompt or terminal, type:

2\. Download Gensim package: Open your anaconda prompt or terminal as administrator and type:

                        OR

```

**代码:**

## 蟒蛇 3

```py
from gensim.utils import lemmatize

sentence = "the bats saw the cats with best stripes hanging upside down by their feet"

lemmatized_sentence = [word.decode('utf-8').split('.')[0] for word in lemmatize(sentence)]

print(lemmatized_sentence)
#> ['bat / NN', 'see / VB', 'cat / NN', 'best / JJ',
#   'stripe / NN', 'hang / VB', 'upside / RB', 'foot / NN']
```

> **注意**:如果上面的代码出现错误，表示**发电机发出停止迭代**。再运行一次。试了 3-4 次就可以了。

在上面的代码中，你可能已经注意到了，gensim 引理者忽略了像******by**这样的词，因为它们不属于上面提到的 4 个引理类别。(名词/动词/形容词/副词)****

******9。Stanford CoreNLP**
CoreNLP 使用户能够导出文本的语言注释，包括标记和句子边界、词性、命名实体、数值和时间值、依存关系和选区解析、情感、引用属性和关系。****

*   ****CoreNLP 是您在 Java 中进行自然语言处理的一站式商店！****
*   ****CoreNLP 目前支持 6 种语言，包括阿拉伯语、汉语、英语、法语、德语和西班牙语。****

```py
****How to use:** 
**1\. Get JAVA 8 :** Download [Java 8](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html) (as per your OS) and install it.

**2\. Get Stanford_coreNLP package :** 
    2.1) Download[**Stanford_CoreNLP**](https://stanfordnlp.github.io/CoreNLP/index.html#download)and unzip it.                   
    2.2) Open terminal 

    (a) go to the directory where you extracted the above file by doing
    **cd C:\Users\...\stanford-corenlp-4.1.0** on terminal

    (b) then, start your Stanford CoreNLP server by executing the following command on terminal: 
    **java -mx4g -cp "*" edu.stanford.nlp.pipeline.StanfordCoreNLPServer -annotators "tokenize, ssplit, pos, lemma, parse, sentiment" -port 9000 -timeout 30000**
    **(leave your terminal open as long as you use this lemmatizer)** 

**3\. Download Standford CoreNLP package:** Open your anaconda prompt or terminal, type:** 
```

******代码:******

## ****蟒蛇 3****

```py
**from stanfordcorenlp import StanfordCoreNLP
import json

# Connect to the CoreNLP server we just started
nlp = StanfordCoreNLP('http://localhost', port = 9000, timeout = 30000)

# Define properties needed to get lemma
props = {'annotators': 'pos, lemma', 'pipelineLanguage': 'en', 'outputFormat': 'json'}

sentence = "the bats saw the cats with best stripes hanging upside down by their feet"
parsed_str = nlp.annotate(sentence, properties = props)
print(parsed_str)

#> "sentences": [{"index": 0,
#  "tokens": [
#        {
#          "index": 1,
#          "word": "the",
#          "originalText": "the",
#          "lemma": "the",           <--------------- LEMMA
#          "characterOffsetBegin": 0,
#          "characterOffsetEnd": 3,
#          "pos": "DT",
#          "before": "",
#          "after": " "
#        },
#        {
#          "index": 2,
#          "word": "bats",
#          "originalText": "bats",
#          "lemma": "bat",           <--------------- LEMMA
#          "characterOffsetBegin": 4,
#          "characterOffsetEnd": 8,
#          "pos": "NNS",
#          "before": " ",
#          "after": " "
#        },
#        {
#          "index": 3,
#          "word": "saw",
#          "originalText": "saw",
#          "lemma": "see",           <--------------- LEMMA
#          "characterOffsetBegin": 9,
#          "characterOffsetEnd": 12,
#          "pos": "VBD",
#          "before": " ",
#          "after": " "
#        },
#        {
#          "index": 4,
#          "word": "the",
#          "originalText": "the",
#          "lemma": "the",          <--------------- LEMMA
#          "characterOffsetBegin": 13,
#          "characterOffsetEnd": 16,
#          "pos": "DT",
#          "before": " ",
#          "after": " "
#        },
#        {
#          "index": 5,
#          "word": "cats",
#          "originalText": "cats",
#          "lemma": "cat",          <--------------- LEMMA
#          "characterOffsetBegin": 17,
#          "characterOffsetEnd": 21,
#          "pos": "NNS",
#          "before": " ",
#          "after": " "
#        },
#        {
#          "index": 6,
#          "word": "with",
#          "originalText": "with",
#          "lemma": "with",          <--------------- LEMMA
#          "characterOffsetBegin": 22,
#          "characterOffsetEnd": 26,
#          "pos": "IN",
#          "before": " ",
#          "after": " "
#        },
#        {
#          "index": 7,
#          "word": "best",
#          "originalText": "best",
#          "lemma": "best",          <--------------- LEMMA
#          "characterOffsetBegin": 27,
#          "characterOffsetEnd": 31,
#          "pos": "JJS",
#          "before": " ",
#          "after": " "
#        },
#        {
#          "index": 8,
#          "word": "stripes",
#          "originalText": "stripes",
#          "lemma": "stripe",          <--------------- LEMMA
#          "characterOffsetBegin": 32,
#          "characterOffsetEnd": 39,
#          "pos": "NNS",
#          "before": " ",
#          "after": " "
#        },
#        {
#          "index": 9,
#          "word": "hanging",
#          "originalText": "hanging",
#          "lemma": "hang",          <--------------- LEMMA
#          "characterOffsetBegin": 40,
#          "characterOffsetEnd": 47,
#          "pos": "VBG",
#          "before": " ",
#          "after": " "
#        },
#        {
#          "index": 10,
#          "word": "upside",
#          "originalText": "upside",
#          "lemma": "upside",          <--------------- LEMMA
#          "characterOffsetBegin": 48,
#          "characterOffsetEnd": 54,
#          "pos": "RB",
#          "before": " ",
#          "after": " "
#        },
#        {
#          "index": 11,
#          "word": "down",
#          "originalText": "down",
#          "lemma": "down",          <--------------- LEMMA
#          "characterOffsetBegin": 55,
#          "characterOffsetEnd": 59,
#          "pos": "RB",
#          "before": " ",
#          "after": " "
#        },
#        {
#          "index": 12,
#          "word": "by",
#          "originalText": "by",
#          "lemma": "by",          <--------------- LEMMA
#          "characterOffsetBegin": 60,
#          "characterOffsetEnd": 62,
#          "pos": "IN",
#          "before": " ",
#          "after": " "
#        },
#        {
#          "index": 13,
#          "word": "their",
#          "originalText": "their",
#          "lemma": "they"#,          <--------------- LEMMA
#          "characterOffsetBegin": 63,
#          "characterOffsetEnd": 68,
#          "pos": "PRP{content}quot;,
#          "before": " ",
#          "after": " "
#        },
#        {
#          "index": 14,
#          "word": "feet",
#          "originalText": "feet",
#          "lemma": "foot",          <--------------- LEMMA
#          "characterOffsetBegin": 69,
#          "characterOffsetEnd": 73,
#          "pos": "NNS",
#          "before": " ",
#          "after": ""
#        }
#      ]
#    }
#  ]**
```

******代码:******

## ****蟒蛇 3****

```py
**# To get the lemmatized sentence as output

# ** RUN THE ABOVE SCRIPT FIRST **

lemma_list = []
for item in parsed_dict['sentences'][0]['tokens']:
    for key, value in item.items():
        if key == 'lemma':
            lemma_list.append(value)

print(lemma_list)
#> ['the', 'bat', 'see', 'the', 'cat', 'with', 'best', 'stripe', 'hang', 'upside', 'down', 'by', 'they', 'foot']

lemmatized_sentence = " ".join(lemma_list)
print(lemmatized_sentence)
#>the bat see the cat with best stripe hang upside down by the foot**
```

******结论:**
所以这些是你在进行自然语言处理项目时可以参考的各种引理化方法。引理化方法的选择完全取决于项目要求。每种方法都有其利弊。对于句子结构很重要的关键项目，如语言应用等，引理化是强制性的。****