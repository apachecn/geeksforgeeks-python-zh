# Python IMDbPY–获取系列的颜色信息

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-the-color-info-of-the-series/](https://www.geeksforgeeks.org/python-imdbpy-getting-the-color-info-of-the-series/)

在这篇文章中，我们将看到如何获得系列的颜色信息，颜色信息基本上是颜色的性质，即关于系列是否多彩的信息，即黑色和白色。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取颜色信息细节

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6468322"

# getting information
series = ia.get_movie(code)

# getting color info of the series
info = series.data['color info']

# printing the object i.e name
print(series)

# print the color info
print(info)
```

**输出:**

```
Money Heist
['Color']
```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6077448"

# getting information
series = ia.get_movie(code)

# getting color info of the series
info = series.data['color info']

# printing the object i.e name
print(series)

# print the color info
print(info)
```

**输出:**

```
Sacred Games
['Color']
```