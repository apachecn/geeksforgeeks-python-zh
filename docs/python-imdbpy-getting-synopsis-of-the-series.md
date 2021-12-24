# Python IMDbPY–获取系列简介

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-系列简介/](https://www.geeksforgeeks.org/python-imdbpy-getting-synopsis-of-the-series/)

在本文中，我们将了解如何获得该系列的概要。剧情简介。梗概是一个简短的总结，让观众了解一篇作文的内容。它概述了故事情节或要点以及作品的其他定义因素，可能包括风格、流派、人物或角色、背景等。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典里得到概要

下面是实现

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6473300"

# getting information
series = ia.get_movie(code)

# getting synopsis of the series
synopsis = series.data['synopsis']

# printing the object i.e name
print(series)

# print the synopsis
print(synopsis)
```

**输出:**

> 米尔萨普
> 【“米尔萨普是一个充满激情的黑帮故事，他们头脑敏锐，幽默无趣，忠诚在瞬间改变，现金规则也变得冰冷。暴力是每天都在发生的事情，完全彻底的控制是目标。政治家、警察、律师和黑手党首领卷入了一个复杂的关系和竞争网络。Akhandanand Tripathi，又名‘Kaleen Bhaiya’，是一位百万富翁地毯出口商，也是米尔扎普尔市的堂(don)，该市位于印度东部 Purvanchal 的一个无法无天的地带腹地。米尔扎普尔是该地区最令人垂涎的权力中心。自 20 年前阿坎达南德的父亲萨蒂亚南达·特里帕蒂在一场血腥的起义中接管这座城市以来，无情的特里帕蒂人一直是米尔萨普无可争议的统治者。阿坎达南德的儿子蒙纳·特里帕蒂渴望权力，为了继承他父亲的遗产，他将不惜一切，这个帝国建立在非法枪支交易和鸦片走私的基础上。但是他自己的父亲认为他还没有准备好入座。古杜和巴布鲁·潘迪特是该市唯一正直的律师和活动家拉玛康德·潘迪特的儿子。古杜和巴布鲁渴望更好的生活，这打破了中产阶级生活的单调乏味，而拉玛康德则东征，与强大的特里帕蒂人对抗。一个不相关的事件，涉及在婚礼队伍中的 Munna，点燃了一系列的事件纠缠特里帕蒂人和潘迪特人的生活。这引发了一场野心、权力、忠诚和贪婪的游戏，最终威胁到特里帕蒂人对米尔扎普尔的控制。”]

另一个例子

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "0903747"

# getting information
series = ia.get_movie(code)

# getting synopsis of the series
synopsis = series.data['synopsis']

# printing the object i.e name
print(series)

# print the synopsis
print(synopsis)
```

**输出:**

```py
['Season 1A struggling high school chemistry teacher.......search the compound.']
```