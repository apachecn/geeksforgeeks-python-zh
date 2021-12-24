# Python IMDbPY–获取系列封面 URL

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-cover-URL-of-the-series/](https://www.geeksforgeeks.org/python-imdbpy-getting-cover-url-of-the-series/)

在这篇文章中，我们将看到我们如何可以获得该系列的封面网址，封面网址基本上是一个网址，当打开时显示该系列的封面图像，封面图像是前面或者我们可以说该系列的海报。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取封面网址的详细信息

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

# getting cover url of the series
cover = series.data['cover url']

# printing the object i.e name
print(series)

# print the cover
print(cover)
```

**输出:**

```py
Money Heist
https://m.media-amazon.com/images/M/MV5BZDcxOGI0MDYtNTc5NS00NDUzLWFkOTItNDIxZjI0OTllNTljXkEyXkFqcGdeQXVyMTMxODk2OTU@._V1_SY150_CR0, 0, 101, 150_.jpg
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

# getting cover url of the series
cover = series.data['cover url']

# printing the object i.e name
print(series)

# print the cover
print(cover)
```

**输出:**

```py
Sacred Games
https://m.media-amazon.com/images/M/MV5BMjJlMjJlMzYtNmU5Yy00N2MwLWJmMjEtNWUwZWIyMGViZDgyXkEyXkFqcGdeQXVyOTAzMTc2MjA@._V1_SY150_CR0, 0, 101, 150_.jpg
```