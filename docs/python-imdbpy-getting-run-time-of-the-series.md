# Python IMDbPY–获取系列的运行时间

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-run-time-of-series/](https://www.geeksforgeeks.org/python-imdbpy-getting-run-time-of-the-series/)

在这篇文章中，我们将看到如何获得系列的运行时间，运行时间基本上是每一集运行多长时间的时间，系列基本上运行时间是长度，即每一集以分钟为单位。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取运行时详细信息

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

# getting runtimes of the series
runtimes = series.data['runtimes']

# printing the object i.e name
print(series)

# print the runtimes
print(runtimes)
```

**输出:**

```
Money Heist
['70']

```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6473300"

# getting information
series = ia.get_movie(code)

# getting runtimes of the series
runtimes = series.data['runtimes']

# printing the object i.e name
print(series)

# print the runtimes
print(runtimes)
```

**输出:**

```
Mirzapur
['60']
```