# Python IMDbPY–获得系列投票数

> 原文:[https://www . geesforgeks . org/python-imdbpy-获得系列投票数/](https://www.geeksforgeeks.org/python-imdbpy-getting-number-of-votes-of-the-series/)

在这篇文章中，我们将看到如何获得该系列的投票数，投票数基本上是投票给该系列并对该系列给出评级的人数，评级是每次投票的平均值。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取投票详情

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6077448"

# getting information
series = ia.get_movie(code)

# getting votes of the series
votes = series.data['votes']

# printing the object i.e name
print(series)

# print the votes
print(votes)
```

**输出:**

```
Sacred Games
65723
```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6468322"

# getting information
series = ia.get_movie(code)

# getting votes of the series
votes = series.data['votes']

# printing the object i.e name
print(series)

# print the votes
print(votes)
```

**输出:**

```
Money Heist
226997
```