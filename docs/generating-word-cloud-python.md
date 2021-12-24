# 在 Python 中生成词云

> 原文:[https://www.geeksforgeeks.org/generating-word-cloud-python/](https://www.geeksforgeeks.org/generating-word-cloud-python/)

单词云是一种数据可视化技术，用于表示文本数据，其中每个单词的大小表示其频率或重要性。使用词云可以突出显示重要的文本数据点。Word clouds 被广泛用于分析来自社交网络网站的数据。

为了在 Python 中生成单词云，需要的模块是——matplotlib、pandas 和单词云。要安装这些软件包，请运行以下命令:

```
pip install matplotlib
pip install pandas
pip install wordcloud
```

用于生成词云的数据集是从 UCI 机器学习资源库收集的。它由 YouTube 上对流行艺术家视频的评论组成。
数据集链接:[https://archive . ics . UCI . edu/ml/机器学习-数据库/00380/](https://archive.ics.uci.edu/ml/machine-learning-databases/00380/)

下面是实现:

## 蟒蛇 3

```
# Python program to generate WordCloud

# importing all necessary modules
from wordcloud import WordCloud, STOPWORDS
import matplotlib.pyplot as plt
import pandas as pd

# Reads 'Youtube04-Eminem.csv' file
df = pd.read_csv(r"Youtube04-Eminem.csv", encoding ="latin-1")

comment_words = ''
stopwords = set(STOPWORDS)

# iterate through the csv file
for val in df.CONTENT:

    # typecaste each val to string
    val = str(val)

    # split the value
    tokens = val.split()

    # Converts each token into lowercase
    for i in range(len(tokens)):
        tokens[i] = tokens[i].lower()

    comment_words += " ".join(tokens)+" "

wordcloud = WordCloud(width = 800, height = 800,
                background_color ='white',
                stopwords = stopwords,
                min_font_size = 10).generate(comment_words)

# plot the WordCloud image                      
plt.figure(figsize = (8, 8), facecolor = None)
plt.imshow(wordcloud)
plt.axis("off")
plt.tight_layout(pad = 0)

plt.show()
```

**输出:**

![](img/ee4b18b8c1534e13ff67750b839db521.png)

上面的单词 cloud 是使用数据集中的 YouTube 04-Amem . CSV 文件生成的。一个有趣的任务可能是使用数据集中可用的其他 csv 文件生成 word clouds。

**字云优势:**

1.  分析客户和员工的反馈。
2.  确定新的搜索引擎优化关键词的目标。

**字云的弊端:**

1.  单词云并不适合所有情况。
2.  数据应该针对上下文进行优化。

**参考资料:**[<u>https://en . Wikipedia . org/wiki/tag _ cloud</u>](https://en.wikipedia.org/wiki/Tag_cloud)