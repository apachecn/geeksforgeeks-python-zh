# Python IMDbPY–获取系列的系列年数

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-series-年份系列/](https://www.geeksforgeeks.org/python-imdbpy-getting-series-years-of-the-series/)

在本文中，我们将了解如何获得系列的系列年。系列年基本上告诉系列的间隔，即发行年份和最后一集播出的年份。如果该系列还没有结束，它将只显示发行年份。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取系列年份

下面是实现

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "0903747"

# getting information
series = ia.get_movie(code)

# getting series year of the series
years = series.data['series years']

# printing the object i.e name
print(series)

# print the series year
print(years)
```

**输出:**

```py
Breaking Bad
2008-2013
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

# getting series year of the series
years = series.data['series years']

# printing the object i.e name
print(series)

# print the series year
print(years)
```

**输出:**

```py
Money Heist
2017-
```