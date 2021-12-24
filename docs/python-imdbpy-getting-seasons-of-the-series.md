# Python IMDbPY–获取系列季节

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-季节系列/](https://www.geeksforgeeks.org/python-imdbpy-getting-seasons-of-the-series/)

在这篇文章中，我们将看到我们如何获得该系列的季节。季节基本上是一组集，它是系列的一个子组，一个系列由许多季节组成。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取季节

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

# getting seasons of the series
season = series.data['seasons']

# printing the object i.e name
print(series)

# print the seasons
print(season)

```

**输出:**

```py
Sacred Games
['1', '2']
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

# getting seasons of the series
season = series.data['seasons']

# printing the object i.e name
print(series)

# print the seasons
print(season)
```

**输出:**

```py
Money Heist
['1', '2', '3', '4']
```