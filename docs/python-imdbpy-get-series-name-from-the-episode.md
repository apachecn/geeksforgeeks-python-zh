# Python IMDbPY–从剧集

中获取剧集名称

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-series-name-from-the-ep1/](https://www.geeksforgeeks.org/python-imdbpy-get-series-name-from-the-episode/)

在本文中，我们将看到如何从剧集信息集中获取剧集名称。每个系列都有季节，每个季节都有多集，即每集是季节的子集，季节是系列的子集。我们通过向剧集添加剧集信息集来获取剧集详细信息。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。使用
> 3 的更新方法为其添加剧集信息集。由于这个对象将作为字典，因此我们必须过滤对象
> 4。借助返回字典
> 5 的数据方法获取对象的主要数据。剧集的每一个键指的是季节，季节的每一个键指的是剧集
> 6。使用“剧集的”作为剧集的关键字来获取父剧集

**注意:**该集还包含一个引用该系列的键，但是要注意，为了避免循环引用，它与我们开始使用的系列对象不是同一个对象

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

print("=========")

# getting episode
epi = episodes[1][1]

# getting series from the episode

get_series = epi['episode of']

# printing the series
print(get_series)
```

**输出:**

```py
Money Heist
=========
Money Heist (TV Series 2017– ) - IMDb

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

print("=========")

# getting episode
epi = episodes[1][1]

# getting series from the episode

get_series = epi['episode of']

# printing the series
print(get_series)
```

**输出:**

```py
Sacred Games
=========
Sacred Games (TV Series 2018– ) - IMDb
```