# Python IMDbPY–获取系列中的季节数量

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-系列季数/](https://www.geeksforgeeks.org/python-imdbpy-getting-number-of-seasons-in-the-series/)

在这篇文章中，我们将看到我们如何获得系列的季节数量，每个系列可以有多个季节，每个季节都有一些集数。系列是季节的集合，即季节是系列的子集。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取季节的数量

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

# getting number of seasons in  the series
count = series.data['number of seasons']

# printing the object i.e name
print(series)

# print the count
print(count)
```

**输出:**

```py
Sacred Games
2
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

# getting number of seasons in  the series
count = series.data['number of seasons']

# printing the object i.e name
print(series)

# print the count
print(count)
```

**输出:**

```py
Money Heist
4

```