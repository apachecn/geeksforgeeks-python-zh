# Python IMDbPY–获取系列的语言代码

> 原文:[https://www . geesforgeks . org/python-imdbpy-获取系列语言代码/](https://www.geeksforgeeks.org/python-imdbpy-getting-the-language-codes-of-the-series/)

在本文中，我们将了解如何获取系列的语言代码，语言代码基本上是系列可用语言的代码，例如英语的“en”和印地语的“hi”。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取语言代码细节

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

# getting language codes of the series
codes = series.data['language codes']

# printing the object i.e name
print(series)

# print the language codes
print(codes)
```

**输出:**

```
Sacred Games
['hi', 'ins', 'mr', 'en']
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

# getting language codes of the series
codes = series.data['language codes']

# printing the object i.e name
print(series)

# print the language codes
print(codes)
```

**输出:**

```
Money Heist
['es', 'ru', 'sr', 'en']
```