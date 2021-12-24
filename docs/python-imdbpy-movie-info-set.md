# Python IMdbpy–电影信息集

> 原文:[https://www.geeksforgeeks.org/python-imdbpy-movie-info-set/](https://www.geeksforgeeks.org/python-imdbpy-movie-info-set/)

IMDb 数据库拥有电影的所有信息，即电影上映时间、分级、地点等，但为了检索它们，会出现问题，因为会有大量的网页，这可能既耗时又耗费带宽，尤其是如果你只对一小部分信息感兴趣的话。

如果我们只想获取特定的信息，我们可以通过向`get_movie`方法传递一个可选的信息参数来获取它。为了获得 IMDb 数据集的信息集，我们将使用`get_movie_infoset`方法。

> **语法:**IMDB _ object . get _ movie _ infoset()
> 
> **论证:**不需要论证。
> 
> **返回:**它返回列表。

下面是实现

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# getting the movie info set of data base
info = ia.get_movie_infoset()

# printing the list 
for element in info:
    print(element)
```

**输出:**

```py
airing
akas
alternate versions
awards
connections
crazy credits
critic reviews
episodes
external reviews
external sites
faqs
full credits
goofs
keywords
locations
main
misc sites
news
official sites
parents guide
photo sites
plot
quotes
release dates
release info
reviews
sound clips
soundtrack
synopsis
taglines
technical
trivia
tv schedule
video clips
vote details

```