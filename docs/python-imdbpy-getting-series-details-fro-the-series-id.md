# Python IMDbPY–获取系列 id 的系列详细信息

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-series-details-for-the-series-id/](https://www.geeksforgeeks.org/python-imdbpy-getting-series-details-fro-the-series-id/)

在本文中，我们将了解如何从 IMDb 数据库中获取剧集细节，就像在 IMDb 网站上一样，每部电视剧以及电视剧的每一集都被视为常规标题，就像电影一样。

> 为此，我们必须执行以下操作–
> 
> 1.借助 get_movie 方法从代码
> 2 中获取系列细节。将此电影对象保存在变量
> 3 中。访问此电影对象类似于字典
> 4。打印所需结果

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

# printing title
print(series.data['title'])

# printing writer name
print(series.data['writer'])
```

**输出:**

```
Mirzapur
[Person id:5883328[http] name:_Karan Anshuman_, Person id:4107081[http] name:_Puneet Krishna_, Person id:10172949[http] name:_Vineet Krishna_]
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

# printing title
print(series.data['title'])

# printing writer name
print(series.data['writer'])
```

**输出:**

```
Sacred Games
[Person id:11351503[http] name:_Abhishek Chaudhary_, Person id:3542598[http] name:_Varun Grover_, Person id:0151512[http] name:_Vikram Chandra_]
```