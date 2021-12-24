# Python IMDbPY–获得该系列的其他(合作)公司

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-other partnered-系列公司/](https://www.geeksforgeeks.org/python-imdbpy-getting-otherpartnered-companies-of-the-series/)

在本文中，我们将了解如何获得该系列的其他公司。其他公司基本上是与该系列相关的合作公司，这些公司不同于生产和分销公司。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典里找出其他公司

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

# getting other companies of the series
companies = series.data['other companies']

# printing the object i.e name
print(series)

# print the companies
print(companies)
```

**输出:**

```py
Mirzapur
[Company id:0293621[http] name:_Trigger Happy Entertainment_]
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

# getting other companies of the series
companies = series.data['other companies']

# printing the object i.e name
print(series)

# print the companies
print(companies)
```

**输出:**

```py
Sacred Games
[Company id:0281702[http] name:_Light & Grips Equipment Hirers India_, Company id:0375072[http] name:_Light n Light_, Company id:0434627[http] name:_Tulsea_]
```