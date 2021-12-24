# Python IMdbpy–设置为人物对象关键点的信息

> 原文:[https://www . geesforgeks . org/python-imdbpy-info-set-to-key-of-person-object/](https://www.geeksforgeeks.org/python-imdbpy-info-set-to-keys-of-person-object/)

在本文中，我们将看到如何将信息集转换为关键点，我们可以通过`get_person_infoset`知道电影的信息集，但是即使在获得信息集后，我们也无法像字典一样使用。

为了使用信息集作为字典关键字，我们必须使用`infoset2keys`方法。

> **语法:** person.infoset2keys
> 
> 这里的电影是 imdb 人物对象
> 
> **执行的操作:**这将允许信息集用作字典键

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "4731677"

# searching the Id and getting info set
person = ia.get_person(code, info =['biography'])

# making infoset to use as keys
person.infoset2keys

# printing bio graphy
print(person['biography'])
```

**输出:**

> ['阿尤斯曼·库拉纳于 1984 年 9 月 14 日出生在印度昌迪加尔。Ayushmann 的职业生涯始于一名受欢迎的电台骑师，最终成为印度 MTV 的 VJ 和印度最受欢迎的主持人之一。2012 年，他凭借《维基捐助者》一炮走红。他在处女作中毫不费力的表演为他赢得了好评，这部电影也成为今年最受欢迎的电影之一。这部古怪的电影加上一些神话般的歌曲，尤其是《帕妮达》(由库拉纳演唱并共同创作)，标志着他进入了印地语电影行业。他还在 2012 年获得了一系列极具声望的奖项。阿尤斯曼是土生土长的旁遮普人，曾就读于昌迪加尔的圣约翰高中和戴维学院。他主修英国文学，拥有昌迪加尔旁遮普大学传播学院大众传播硕士学位。他做了五年的严肃戏剧。他也是 DAV 学院的“Aaghaaz”和“Manchtantra”的创始人，这是昌迪加尔活跃的戏剧团体。他在街头戏剧中构思和表演，并在国家大学节日中获奖，如 Mood Indigo (IIT 孟买)、Oasis(比拉科技学院，皮拉尼)和 St. Bedes Simla。他还因在达拉谟·巴拉蒂的《安德哈·尤格》中扮演阿什瓦特哈马而获得最佳男演员奖。从剧院到电视再到大银幕，阿尤斯曼作为艺术家的发展是最有机的发展之一。他接下来演了一些他的表演受到观众和评论家高度赞赏的电影。阿尤斯曼同时作为歌手和现场表演者创作了他的全部作品。他的三首单曲《奥赫里耶》、《米蒂·迪·库施布》和最新的《叶欣·胡恩大街》赢得了数百万人的心。* Nishanth ']

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "2690647"

# searching the Id and getting info set
person = ia.get_person(code, info =['filmography'])

# making infoset to use as keys
person.infoset2keys

# printing filmo graphy
print(person['filmography'])
```

**输出:**

```
[{'actor': [Movie id:11261278[http] title:_Romeo (2020)_.......(2018)_]}]
```