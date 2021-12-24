# 使用 Word2Vec 嵌入从给定单词中找到单词类比

> 原文:[https://www . geesforgeks . org/find-the-word-类比-从给定的单词-使用-word 2 vec-embedding/](https://www.geeksforgeeks.org/finding-the-word-analogy-from-given-words-using-word2vec-embeddings/)

在许多分班考试中，我们经常会遇到一个基本问题来寻找单词类比。在单词类比任务中，我们完成句子“ **a 是 to b 就像 c 是 to _ _**”，常表示为 **a : b :: c : d** ，我们要找到单词‘d’。一个示例问题可以是这样的:“**男人对女人就像国王对 __** ”。

人脑可以识别出空白处必须填入单词“ **queen** ”。但是对于一台机器来说，要理解这种模式，并用最合适的词来填补空白，需要进行大量的训练。如果我们可以使用机器学习算法来自动完成寻找类比这个词的任务，会怎么样。在本教程中，我们将使用 **Word2Vec** 模型和一个名为“**Google news-vectors-negative 300 . bin**的预训练模型，该模型由 Google 在超过 500 亿个单词上进行训练。预训练数据集中的每个单词都被嵌入到 300 维空间中，并且上下文/含义相似的单词在空间中被放置得彼此更靠近。

**找出类比词的方法:**

在这个问题中，我们的目标是找到一个单词 **d** ，使得关联的单词向量 **va，vb，vc，vd** 按照以下关系相互关联:**VB–va = VD–VC**。我们将使用余弦相似度来测量 **vb-va** 和 **vd-vc** 之间的相似度。

**导入重要库:**

我们需要安装一个额外的 **gensim** 库，要使用 word2vec 模型，要安装 gensim 使用命令 **'** ***pip 在您的终端/命令提示符下安装 gensim*** **'** 。

## 蟒蛇 3

```py
import numpy as np
import gensim
from gensim.models import word2vec,KeyedVectors
from sklearn.metrics.pairwise import cosine_similarity
```

**使用预训练模型加载单词向量:**

## 蟒蛇 3

```py
vector_word_notations = KeyedVectors.load_word2vec_format('GoogleNews-vectors-negative300.bin',binary=True)
```

**定义一个预测类比词的函数:**

## 蟒蛇 3

```py
def analogous_word(word_1,word_2,word_3,vector_word_notations):
    ''' The function accepts a triad of words, word_1, word_2, word_3 and returns word_4 such that word_1:word_2::word_3:word_4 '''

    # converting each word to its lowercase
    word_1,word_2,word_3 = word_1.lower(),word_2.lower(),word_3.lower()

    # Similarity between |word_2-word_1| = |word_4-word_3| should be maximum
    maximum_similarity = -99999

    word_4 = None

    words = vector_word_notations.vocab.keys()

    va,vb,vc = vector_word_notations[word_1],\
    vector_word_notations[word_2],vector_word_notations[word_3]

    # to find word_4 such that similarity
    # (|word_2 - word_1|, |word_4 - word_3|) should be maximum

    for i in words:
        if i in [word_1,word_2,word_3]:
            continue

        wvec = vector_word_notations[i]
        similarity = cosine_similarity(,[wvec-vc])

        if similarity > maximum_similarity:
            maximum_similarity = similarity
            word_4 = i     

    return word_4
```

**测试我们的模型:**

## 蟒蛇 3

```py
triad_1 = ("Man","Woman","King")
# *triad_1 is written to unpack the elements in the tuple
output = analogous_word(*triad_1,word_vectors) 
print(output)

# The output will be shown as queen
```