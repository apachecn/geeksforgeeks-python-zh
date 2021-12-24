# Python IMDbPY–将信息集添加到搜索到的电影中

> 原文:[https://www . geesforgeks . org/python-imdbpy-add-info-set-to-search-movies/](https://www.geeksforgeeks.org/python-imdbpy-adding-info-set-to-the-searched-movies/)

在本文中，我们将看到如何向搜索的电影中添加信息集，搜索电影检索固定的数据集，并且没有信息集的概念。因此，电影对象的信息将比默认信息集更少。例如，如果您使用搜索方法，结果中的影片对象将不会有许多在影片获取方法中可用的键。

为了给搜索到的电影添加信息集，我们将使用`update`方法。

> **语法:**IMDB _ object . update(movie _ object，info = ['plot '，' tagline '])
> 
> **参数:**需要两个参数，一个是我们想要更多信息的电影对象，另一个是信息集，即按键列表
> 
> **执行的操作:**将检索信息集信息

以下是实施–

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name
name = "3 idiots"

# searching the name
movies = ia.search_movie(name)

movie = movies[0]

# getting more information
ia.update(movie, info = ['taglines'])

# printing tagline
print(movie['taglines'])
```

**输出:**

```
["Don't be Stupid. Be an I.D.I.O.T."]
```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name
name = "Success story"

# searching the name
movies = ia.search_movie(name)

movie = movies[0]

# getting more information
ia.update(movie, info = ['plot'])

# printing plot
print(movie['plot'])
```

**输出:**

> 【“Panagis Pandoras:一个富有的精神病医生，来自出版背景，迷人而肆无忌惮。Tzortzina Tzelepi:一个失业的女演员，一对资产阶级夫妇的女儿，美丽，立志成功。他们两个，尽管截然相反，却突然坠入爱河，不顾一切地热烈地，然后结婚了。为了适应帕纳吉斯的世界，佐尔齐纳不顾一切地否认自己的真实身份。她创造性的死胡同，加上艰难的怀孕，彻底改变了她，因为她开始意识到她的婚姻生活中没有什么是她想象的那样。财务状况的彻底改变，帕纳吉斯的父亲因债务自杀，以及帕纳吉斯即将涉足政治，加剧了他们之间的分歧。钦佩、激情和吸引力现在让位于失望、孤立和对抗。然后，残酷开始了，他们的爱情故事最终变成了一个复仇和仇恨的故事，因为他们都为了生存而诉诸极端。”]