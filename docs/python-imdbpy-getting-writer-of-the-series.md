# Python IMDbPY–获得系列的作者

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-writer-of-the-series/](https://www.geeksforgeeks.org/python-imdbpy-getting-writer-of-the-series/)

在本文中，我们将了解如何找到该系列的作者。作家基本上是写整个系列故事的人，一个系列可以有多个作家。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典里找出作者

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

# getting wruters of the series
writer = series.data['writer']

# printing the object i.e name
print(series)

# print the writers
print(writer)
```

**输出:**

```
Money Heist
[Person id:1210565[http] name:_Álex Pina_, Person id:8996721[http] name:_Javier Gómez Santander_, Person id:2651446[http] name:_Esther Martínez Lobato_]
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

# getting wruters of the series
writer = series.data['writer']

# printing the object i.e name
print(series)

# print the writers
print(writer)
```

**输出:**

```
Sacred Games
[Person id:11351503[http] name:_Abhishek Chaudhary_, Person id:3542598[http] name:_Varun Grover_, Person id:0151512[http] name:_Vikram Chandra_]
```