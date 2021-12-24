# Python IMdbpy–有点像系列

> 原文:[https://www . geeksforgeeks . org/python-imdbpy-get-同类系列/](https://www.geeksforgeeks.org/python-imdbpy-getting-kind-of-the-series/)

在本文中，我们将了解如何获得该系列的类型。善良基本上是告诉什么类型的系列，例如"电视剧"或"电影"等。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取详细信息

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

# getting kind of the series
kind = series.data['kind']

# printing the object i.e name
print(series)

# print the kind
print(kind)
```

**输出:**

```py
Sacred Games
tv series
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

# getting kind of the series
kind = series.data['kind']

# printing the object i.e name
print(series)

# print the kind
print(kind)
```

**输出:**

```py
Money Heist
tv series
```