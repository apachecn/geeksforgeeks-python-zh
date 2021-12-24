# Python IMDbPY–获得该系列的评级

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-rating-of-the-series/](https://www.geeksforgeeks.org/python-imdbpy-getting-rating-of-the-series/)

在这篇文章中，我们将看到我们如何获得该系列的评分，在 IMDb 的评分是从 10 分开始给出的。评分是基于观众的体验，评分越高意味着观众非常满意，或者换句话说，他们喜欢这部电影。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取评级详细信息

下面是实现

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6468322"

# getting information
series = ia.get_movie(code)

# getting rating of the series
rating = series.data['rating']

# printing the object i.e name
print(series)

# print the rating
print(rating)
```

**输出:**

```py
Money Heist
8.5
```

另一个例子

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6077448"

# getting information
series = ia.get_movie(code)

# getting rating of the series
rating = series.data['rating']

# printing the object i.e name
print(series)

# print the rating
print(rating)
```

**输出:**

```py
Sacred Games
8.7
```