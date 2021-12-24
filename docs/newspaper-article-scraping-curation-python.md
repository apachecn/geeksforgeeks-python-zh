# 报纸:文章刮&策展(Python)

> 原文:[https://www . geesforgeks . org/news-article-scratch-curating-python/](https://www.geeksforgeeks.org/newspaper-article-scraping-curation-python/)

报纸是一个 Python 模块，用于提取和解析报纸文章。报纸使用先进的网络抓取算法从网站上提取所有有用的文本。它在网上报纸网站上运行得非常好。因为它使用网页抓取对报纸网站的太多请求可能会导致阻塞，所以相应地使用它。

安装:

```py
pip install newspaper3k
```

报纸支持以下语言:

```py
  input code         full name
  ar               Arabic
  da               Danish
  de               German
  el               Greek
  en               English
  it               Italian
  zh               Chinese
......... and many more
```

创建文章实例的一些有用功能

```py
article_name = Article(url, language="language code according to newspaper")
```

下载文章

```py
article_name.download()
```

分析一篇文章

```py
article_name.parse()
```

将自然语言处理应用于文章

```py
article_name.nlp()
```

摘抄文章正文

```py
article_name.text
```

摘抄文章标题

```py
article_name.title
```

摘录文章摘要

```py
article_name.summary
```

提取文章的关键词

```py
article_name.keywords
```

## 计算机编程语言

```py
from newspaper import Article

#A new article from TOI
url = "http:// timesofindia.indiatimes.com/world/china/chinese-expert-warns-of-troops-entering-kashmir/articleshow/59516912.cms"

#For different language newspaper refer above table
toi_article = Article(url, language="en") # en for English

#To download the article
toi_article.download()

#To parse the article
toi_article.parse()

#To perform natural language processing ie..nlp
toi_article.nlp()

#To extract title
print("Article's Title:")
print(toi_article.title)
print("n")

#To extract text
print("Article's Text:")
print(toi_article.text)
print("n")

#To extract summary
print("Article's Summary:")
print(toi_article.summary)
print("n")

#To extract keywords
print("Article's Keywords:")
print(toi_article.keywords)
```

**输出:**

```py
Article's Title:
India China News: Chinese expert warns of troops entering Kashmir

Article's Text:
BEIJING: A Chinese expert has argued that his country's troops would be entitled to enter the Indian side of Kashmir by extending the logic that has permitted Indian troops to enter an area which is disputed by China and Bhutan This is one of the several arguments made by the scholar in an attempt to blame India for. India has responded to efforts by China to build a road in the Doklam area, which falls next to the trijunction connecting Sikkim with Tibet and Bhutan and"Even if India were requested to defend Bhutan's territory, this could only be limited to its established territory, not the disputed area, " Long Xingchun, director of the Center for Indian Studies at China West Normal University said in an article. "Otherwise, under India's logic, if the Pakistani government requests, a third country's army can enter the area disputed by India and Pakistan, including India-controlled Kashmir".China is not just interfering, it is building roads and other infrastructure projects right inside Pakistan-Occupied Kashmir (PoK), which is claimed by both India and Pakistan. This is one of the facts that the article did not mention.The scholar, through his article in the Beijing-based Global Times, suggested that Beijing can internationalize the Doklam controversy without worrying about western countries supporting India because the West has a lot of business to do with China."China can show the region and the international community or even the UN Security Council its evidence to illustrate China's position, " Long said. At the same time, he complained that "Western governments and media kept silent, ignoring India's hegemony over the small countries of South Asia" when India imposed a blockade on the flow of goods to Nepal in 2015.Recent actions by US president Donald Trump, which include selling arms to Taiwan and pressuring China on the North Korean issue, shows that the West is not necessarily cowered down by China's business capabilities.He reiterated the government's stated line that Doklam belongs to China, and that Indian troops had entered the area under the guise of helping Bhutan protect its territory."For a long time, India has been talking about international equality and non-interference in the internal affairs of others, but it has pursued hegemonic diplomacy in South Asia, seriously violating the UN Charter and undermining the basic norms of international relations, " he said.Interestingly, Chinese scholars are worrying about India interfering in Bhutan's "sovereignty and national interests" even though it is Chinese troops who have entered the Doklam area claimed by it."Indians have migrated in large numbers to Nepal and Bhutan, interfering with Nepal's internal affairs. The first challenge for Nepal and Bhutan is to avoid becoming a state of India, like Sikkim, " he said.

Article's Summary:
sending its troops to the disputed Doklam area +puts Indian territory at risk +BEIJING: A Chinese expert has argued that his country's troops would be entitled to enter the Indian side of Kashmir by extending the logic that has permitted Indian troops to enter an area which is disputed by China and Bhutan This is one of the several arguments made by the scholar in an attempt to blame India for.
"Otherwise, under India's logic, if the Pakistani government requests, a third country's army can enter the area disputed by India and Pakistan, including India-controlled Kashmir".China is not just interfering, it is building roads and other infrastructure projects right inside Pakistan-Occupied Kashmir (PoK), which is claimed by both India and Pakistan.
"China can show the region and the international community or even the UN Security Council its evidence to illustrate China's position, " Long said.
"Indians have migrated in large numbers to Nepal and Bhutan, interfering with Nepal's internal affairs.
The first challenge for Nepal and Bhutan is to avoid becoming a state of India, like Sikkim, " he said.

Article's Keywords:
['troops', 'india', 'china', 'territory', 'west', 'disputed', 'expert', 'indian', 'bhutan', 'kashmir', 'chinese', 'entering', 'doklam', 'area', 'warns']
```

参考:[github 上的报纸 python 包](https://github.com/codelucas/newspaper/)

本文由 [**普拉蒂克·查哈尔**](https://github.com/pratik-chhajer) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。