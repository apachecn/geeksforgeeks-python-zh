# Python IMDbPY–剧集每一季总集数

> 原文:[https://www . geesforgeks . org/python-imdbpy-剧集每季总集数/](https://www.geeksforgeeks.org/python-imdbpy-total-number-of-episode-of-each-season-of-the-series/)

在本文中，我们将了解如何从剧集信息集中获取该系列每一季的总集数。每个系列都有季节，每个季节都有多集，即每集是季节的子集，季节是系列的子集。我们通过向剧集添加剧集信息集来获得剧集

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。使用
> 3 的更新方法为其添加剧集信息集。由于这个对象将作为字典，因此我们必须过滤对象
> 4。借助返回字典
> 5 的数据方法获取对象的主要数据。从词典中获取剧集本词典的关键词是季节
> 6。获取每个键值的长度将给出每个季节的总集数

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

# adding new info set
ia.update(series, 'episodes')

# getting episodes of the series
episodes = series.data['episodes']

# printing the object i.e name
print(series)

# printing total episodes of each season
# traversing each key
for i in episodes.keys():

    # getting total episode in season i
    n = len(episodes[i])

    # printing total episodes
    print("Total Episodes in Season " + str(i) + " : " + str(n))
```

**输出:**

```py
Sacred Games
Total Episodes in Season 2 : 8
Total Episodes in Season 1 : 8
```

另一个例子

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

# printing total episodes of each season
# traversing each key
for i in episodes.keys():

    # getting total episode in season i
    n = len(episodes[i])

    # printing total episodes
    print("Total Episodes in Season " + str(i) + " : " + str(n))
```

**输出:**

```py
Money Heist
Total Episodes in Season 4 : 8
Total Episodes in Season 1 : 9
Total Episodes in Season 2 : 6
Total Episodes in Season 3 : 8
```