# Python IMDbPY–获取系列的剧情大纲

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-plot-系列概述/](https://www.geeksforgeeks.org/python-imdbpy-getting-plot-outline-of-the-series/)

在这篇文章中，我们将看到如何获得该系列的情节大纲。情节大纲是讲述一个故事的散文，可以改编成电影剧本。有时因为它的长度，它被称为“一页”。它通常比标准大纲更长、更详细，标准大纲通常只有一两个段落，但比治疗或步骤大纲更短、更不详细。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取情节大纲细节

下面是实现

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6077448"

# getting information
series = ia.get_movie(code)

# getting plot outline of the series
outline = series.data['plot outline']

# printing the object i.e name
print(series)

# print the outline
print(outline)
```

**输出:**

```py
Sacred Games
Sartaj Singh, a Mumbai police officer, receives an anonymous phone call from a gangster who threatens to blow up the entire city. Amid the corrupt standards of Indian law enforcement begins a battle between a 'nobody' cop and ruthless gangster who perceives (sometimes) himself to be a God.

```

另一个例子

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6473300"

# getting information
series = ia.get_movie(code)

# getting plot outline of the series
outline = series.data['plot outline']

# printing the object i.e name
print(series)

# print the outline
print(outline)
```

**输出:**

> 米尔扎普尔
> 铁腕的阿坎达南德·特里帕蒂是百万富翁地毯出口商，也是米尔扎普尔的黑手党头目。他的儿子，蒙纳，是一个不值得的，渴望权力的继承人，他会不惜一切代价继承他父亲的遗产。婚礼队伍中的一个事件迫使他与正直的律师拉玛康德·潘迪特以及他的儿子古杜和巴布鲁相遇。它滚雪球般变成野心、权力和贪婪的游戏，威胁着这座无法无天的城市的结构！