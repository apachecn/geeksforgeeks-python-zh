# Python IMDbPY–获取系列每一季的每集 ID

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-每集-剧集每季 id/](https://www.geeksforgeeks.org/python-imdbpy-get-each-episode-id-of-each-season-of-the-series/)

在本文中，我们将看到如何从剧集信息集中获取该系列每一季每集的 id。每个系列都有季节，每个季节都有多集，即每集是季节的子集，季节是系列的子集。我们通过向剧集
添加剧集信息集来获取剧集详情

> 为了实现这一点，我们必须执行以下操作–
> 1。借助 get_movie 方法
> 2 获取系列详情。使用
> 3 的更新方法为其添加剧集信息集。由于这个对象将作为字典，因此我们必须过滤对象
> 4。借助返回字典
> 5 的数据方法获取对象的主要数据。剧集的每一个键指的是季节，季节的每一个键指的是剧集
> 6。获取每集的 id 并打印出来

下面是实现

## 蟒蛇 3

```
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

# getting season
season = episodes[1]

# getting single episode of season
epi = season[1]

# getting id and printing it
get_id = epi.getID

print(get_id)
```

**输出:**

```
Money Heist
=========
bound method Movie.getID of <Movie id:6807344[http] title:_"Money Heist (TV Series 2017– ) - IMDb" Efectuar lo acordado (2017)_
```

另一个例子

## 蟒蛇 3

```
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

# getting season
season = episodes[1]

# getting single episode of season
epi = season[1]

# getting id and printing it
get_id = epi.getID

print(get_id)
```

**输出:**

```
Sacred Games
=========
bound method Movie.getID of Movie id:8058636[http] title:_"Sacred Games (TV Series 2018– ) - IMDb" Ashwathama (2018)_
```