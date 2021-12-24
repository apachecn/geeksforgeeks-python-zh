# 在 Python 中生成词云|集合 2

> 原文:[https://www . geesforgeks . org/generating-word-cloud-in-python-set-2/](https://www.geeksforgeeks.org/generating-word-cloud-in-python-set-2/)

先决条件:[在 Python 中生成单词云| Set–1](https://www.geeksforgeeks.org/generating-word-cloud-python/)
单词云是一种数据可视化技术，用于表示文本数据，其中每个单词的大小表示其频率或重要性。使用词云可以突出显示重要的文本数据点。Word clouds 被广泛用于分析来自社交网络网站的数据。
为了在 Python 中生成单词云，需要的模块有–matplotlib、pandas 和单词云。要安装这些软件包，请运行以下命令:

```py
pip install matplotlib
pip install pandas
pip install wordcloud
```

要获取所用 csv 文件的链接，请单击此处的。
**代码#1:字数**
可以设置标签云显示的最大字数。为此，请使用 WordCloud()函数的 max_words 关键字参数。

## 蟒蛇 3

```py
# importing the necessary modules
from wordcloud import WordCloud
import matplotlib.pyplot as plt
import csv

# file object is created
file_ob = open(r"C:/Users/user/Documents/sample.csv")

# reader object is created
reader_ob = csv.reader(file_ob)

# contents of reader object is stored .
# data is stored in list of list format.
reader_contents = list(reader_ob)

# empty string is declare
text = ""

# iterating through list of rows
for row in reader_contents :

    # iterating through words in the row
    for word in row :

        # concatenate the words
        text = text + " " + word

# show only 10 words in the wordcloud .
wordcloud = WordCloud(width=480, height=480, max_words=10).generate(text)

# plot the WordCloud image
plt.figure()
plt.imshow(wordcloud, interpolation="bilinear")
plt.axis("off")
plt.margins(x=0, y=0)
plt.show()
```