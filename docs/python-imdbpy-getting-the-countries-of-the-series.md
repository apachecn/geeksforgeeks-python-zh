# Python IMDbPY–获取系列的国家/地区

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-the-country-of-the-series/](https://www.geeksforgeeks.org/python-imdbpy-getting-the-countries-of-the-series/)

在本文中，我们将看到我们如何获得系列的国家，有些系列是基于国家的，即整个故事围绕单个国家，尽管有些系列的故事围绕多个国家。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取国家的详细信息

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6473300"

# getting information
series = ia.get_movie(code)

# getting countries of the series
countries = series.data['countries']

# printing the object i.e name
print(series)

# print the countries
print(countries)
```

**输出:**

```
Mirzapur
['India']
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

# getting countries of the series
countries = series.data['countries']

# printing the object i.e name
print(series)

# print countries
print(countries)
```

**输出:**

```
Money Heist
['Spain']
```