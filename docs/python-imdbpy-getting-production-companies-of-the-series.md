# Python IMDbPY–获得该系列的生产公司

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-production-of-companies-of-the-series/](https://www.geeksforgeeks.org/python-imdbpy-getting-production-companies-of-the-series/)

在本文中，我们将了解如何获得该系列的生产公司。生产公司是生产该系列的公司，例如网飞等。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典里找生产公司

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

# getting production companies of the series
companies = series.data['production companies']

# printing the object i.e name
print(series)

# print the companies
print(companies)
```

**输出:**

```
Sacred Games
[Company id:0144901[http] name:_Netflix_, Company id:0077343[http] name:_Phantom Films_, Company id:0362371[http] name:_Phantom Films_]
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

# getting production companies of the series
companies = series.data['production companies']

# printing the object i.e name
print(series)

# print the companies
print(companies)
```

**输出:**

```
Money Heist
[Company id:0445833[http] name:_Atresmedia_, Company id:0625845[http] name:_Vancouver Media_]
```