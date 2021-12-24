# Python IMDbPY–获得该系列的演员表

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-cast-of-the-series/](https://www.geeksforgeeks.org/python-imdbpy-getting-cast-of-the-series/)

在本文中，我们将了解如何获得该系列的演员阵容。演员阵容基本上是一群在这个系列中工作的演员，他们也可以是导演或演员。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典里找演员

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "0903747"

# getting information
series = ia.get_movie(code)

# getting cast of the series
cast = series.data['cast']

# printing the object i.e name
print(series)

# print the cast person at index 0
print(cast[0])
```

**输出:**

```
Breaking Bad
Bryan Cranston
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

# getting cast of the series
cast = series.data['cast']

# printing the object i.e name
print(series)

# print the cast
for i in range(3):
    print(cast[i])
```

**输出:**

```
Sacred Games
Saif Ali Khan
Nawazuddin Siddiqui
Neeraj Kabi
```