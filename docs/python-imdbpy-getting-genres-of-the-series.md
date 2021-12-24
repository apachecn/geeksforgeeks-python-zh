# Python IMDbPY–获取系列的流派

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-流派-of-the-series/](https://www.geeksforgeeks.org/python-imdbpy-getting-genres-of-the-series/)

在这篇文章中，我们将看到我们如何可以得到系列的流派，流派基本上是类别来划分一个系列，例如浪漫，戏剧，行动等。

> 为了获得电影的类型，我们必须做以下工作–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取流派的详细信息

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

# getting gerne of the series
genre = series.data['genres']

# printing the object i.e name
print(series)

# print the gerne
print(genre)
```

**输出:**

```py
Sacred Games
['Action', 'Crime', 'Drama', 'Thriller']
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

# getting gerne of the series
genre = series.data['genres']

# printing the object i.e name
print(series)

# print the gerne
print(genre)
```

```py
Mirzapur
['Action', 'Crime', 'Drama', 'Thriller']
```