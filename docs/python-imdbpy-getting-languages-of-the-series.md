# Python IMDbPY–获取系列语言

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-languages-of-the-series/](https://www.geeksforgeeks.org/python-imdbpy-getting-languages-of-the-series/)

在本文中，我们将了解如何获得该系列的语言。一个系列有多种语言版本，因为有大量的观众，他们倾向于用他们的语言制作系列，这样他们可以聚集越来越多的观众。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取语言的详细信息

下面是实现

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6473300"

# getting information
series = ia.get_movie(code)

# getting languages of the series
languages = series.data['languages']

# printing the object i.e name
print(series)

# print the languages
print(languages)
```

**输出:**

```py
Mirzapur
['Hindi']
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

# getting languages of the series
languages = series.data['languages']

# printing the object i.e name
print(series)

# print the languages
print(languages)
```

**输出:**

```py
Money Heist
['Spanish', 'Russian', 'Serbian', 'English']
```