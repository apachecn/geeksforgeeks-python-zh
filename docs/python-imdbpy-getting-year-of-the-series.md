# Python IMDbPY–年度最佳系列

> 原文:[https://www . geesforgeks . org/python-imdbpy-获得年度最佳系列/](https://www.geeksforgeeks.org/python-imdbpy-getting-year-of-the-series/)

在本文中，我们将了解如何获得年度系列。一年基本上是剧集发行的一年，也就是第一集播出的那一年。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取年份的详细信息

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6468322"

# getting information
series = ia.get_movie(code)

# getting year of the series
year = series.data['year']

# printing the object i.e name
print(series)

# print the year
print(year)
```

**输出:**

```
Money Heist
2017
```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6077448"

# getting information
series = ia.get_movie(code)

# getting year of the series
year = series.data['year']

# printing the object i.e name
print(series)

# print the year
print(year)
```

**输出:**

```
Sacred Games
2018

```