# Python IMDbPY–获取系列的国家代码

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-the-country-codes-of-the-series/](https://www.geeksforgeeks.org/python-imdbpy-getting-the-country-codes-of-the-series/)

在本文中，我们将了解如何获取系列的国家代码，有些系列是基于国家的，即整个故事围绕单个国家展开，尽管有些系列故事围绕多个国家展开，每个国家都有国家代码，例如印度的“In”。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取国家代码的详细信息

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

# getting countries of the series
country_codes = series.data['country codes']

# printing the object i.e name
print(series)

# print the country codes
print(country_codes)
```

**输出:**

```py
Money Heist
['es']
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

# getting countries of the series
country_codes = series.data['country codes']

# printing the object i.e name
print(series)

# print the country codes
print(country_codes)
```

**输出:**

```py
Sacred Games
['in', 'us']
```