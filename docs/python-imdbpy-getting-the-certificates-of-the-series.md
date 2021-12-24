# Python IMDbPY–获取系列证书

> 原文:[https://www . geesforgeks . org/python-imdbpy-获取系列证书/](https://www.geeksforgeeks.org/python-imdbpy-getting-the-certificates-of-the-series/)

在这篇文章中，我们将看到我们如何才能获得系列证书，证书基本上是给每个系列的证书，它讲述了电影的性质，如年龄限制证书每个证书因国家而异。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取证书详细信息

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

# getting certificates of the series
certificate = series.data['certificates']

# printing the object i.e name
print(series)

# print the certificate
print(certificate)
```

**输出:**

```py
Money Heist
['Argentina:16', 'Australia:MA15+::(Netflix self-rating)', 'Brazil:16', 'Canada:TV-MA::(self-applied)', 'France:16', 'Germany:16', 'India:16+::(self-applied)', 'Italy:VM14', 'Japan:R18+::(self-applied)', 'Mexico:TV-MA::(self-applied)', 'Netherlands:12::(season 1)', 'Netherlands:16::(seasons 2-4)', 'Singapore:M18', 'South Korea:18', 'Spain:16', 'Turkey:15+', 'United Kingdom:15', 'United Kingdom:18::(season 4)', 'United States:TV-MA', 'Vietnam:C18']
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

# getting certificates of the series
certificate = series.data['certificates']

# printing the object i.e name
print(series)

# print the certificate
print(certificate)
```

**输出:**

> 神圣运动会
> [“阿根廷:16 人”、“澳大利亚:MA15+”、“巴西:18 人::(自行申请)”、“法国:16 人”、“德国:16 人”、“印度:A”、“印度:UA::(预告片)”、“意大利:VM18”、“荷兰:16 人”、“挪威:16 人::(网飞自行评定)”、“新加坡:R21”、“韩国:18 人”、“西班牙:16 人”、“英国:18 人”、“美国:TV-MA::(网飞)”]