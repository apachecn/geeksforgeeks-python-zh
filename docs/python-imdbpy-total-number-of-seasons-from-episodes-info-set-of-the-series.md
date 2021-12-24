# Python IMDbPY–剧集信息集中的季节总数

> 原文:[https://www . geesforgeks . org/python-imdbpy-总集数-剧集-信息-剧集集/](https://www.geeksforgeeks.org/python-imdbpy-total-number-of-seasons-from-episodes-info-set-of-the-series/)

在本文中，我们将了解如何从剧集信息集中获取该系列的总季数。每个系列都有季节，每个季节都有多集，即每集是季节的子集，季节是系列的子集。我们通过向剧集添加剧集信息集来获得剧集。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。使用
> 3 的更新方法为其添加剧集信息集。由于这个对象将作为字典，因此我们必须过滤对象
> 4。借助返回字典
> 5 的数据方法获取对象的主要数据。从词典中获取剧集本词典的关键词是季节
> 6。获取键的长度，这将给出季节的总数

下面是实现

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6468322"

# getting information
series = ia.get_movie(code)

# adding new info set
ia.update(series, 'episodes')

# getting episodes of the series
episodes = series.data['episodes']

# printing the object i.e name
print(series)

# getting total seasons
n = len(episodes.keys())

# print value of n
print("Total seasons = " + str(n))
```

**输出:**

```py
Money Heist
Total seasons = 4
```

另一个例子

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6077448"

# getting information
series = ia.get_movie(code)

# adding new info set
ia.update(series, 'episodes')

# getting episodes of the series
episodes = series.data['episodes']

# printing the object i.e name
print(series)

# getting total seasons
n = len(episodes.keys())

# print value of n
print("Total seasons = " + str(n))
```

**输出:**

```py
Sacred Games
Total seasons = 2
```