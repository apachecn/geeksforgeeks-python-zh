# Python IMDbPY–获取系列每一季的每集名称

> 原文:[https://www . geeksforgeeks . org/python-imdbpy-get-每集-剧集名称/](https://www.geeksforgeeks.org/python-imdbpy-get-each-episode-name-of-each-season-of-the-series/)

在本文中，我们将了解如何从剧集信息集中获取该系列每一季每集的名称/标题。每个系列都有季节，每个季节都有多集，即每集是季节的子集，季节是系列的子集。我们通过向剧集添加剧集信息集来获得剧集

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。使用
> 3 的更新方法为其添加剧集信息集。由于这个对象将作为字典，因此我们必须过滤对象
> 4。借助返回字典
> 5 的数据方法获取对象的主要数据。剧集的每一个键指的是季节，季节的每一个键指的是剧集
> 6。打印每集的标题

下面是实现

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6077448"

# getting information
series = ia.get_movie(code)

# adding new info set
ia.update(series, 'episodes')

# getting episodes of the series
episodes = series.data['episodes']

# printing the object i.e name
print(series)

print("=========")

# traversing each key
for i in episodes.keys():

    # printing season number
    print("Season" + str(i))

    # traversing season i
    for j in episodes[i]:

        # getting title of episode
        title = episodes[i][j]['title']

        # printing title
        print(" Ep" + str(j) + " : " + title)
```

**输出:**

```py
Sacred Games
=========
Season2
 Ep1 : Matsya
 Ep2 : Siduri
 Ep3 : Apasmara
 Ep4 : Bardo
 Ep5 : Vikarna
 Ep6 : Azrael
 Ep7 : Torino
 Ep8 : Radcliffe
Season1
 Ep1 : Ashwathama
 Ep2 : Halahala
 Ep3 : Aatapi Vatapi
 Ep4 : Brahmahatya
 Ep5 : Sarama
 Ep6 : Pretakalpa
 Ep7 : Rudra
 Ep8 : Yayati
```

另一个例子

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6473300"

# getting information
series = ia.get_movie(code)

# adding new info set
ia.update(series, 'episodes')

# getting episodes of the series
episodes = series.data['episodes']

# printing the object i.e name
print(series)

print("=========")

# traversing each key
for i in episodes.keys():

    # printing season number
    print("Season" + str(i))

    # traversing season i
    for j in episodes[i]:

        # getting title of episode
        title = episodes[i][j]['title']

        # printing title
        print(" Ep" + str(j) + " : " + title)

```

**输出:**

```py
Mirzapur
=========
Season1
 Ep1 : Jhandu
 Ep2 : Gooda
 Ep3 : Wafadar
 Ep4 : Virginity
 Ep5 : Bhaukal
 Ep6 : Barfi
 Ep7 : Lions of Mirzapur
 Ep8 : Tandav
 Ep9 : Yogya
```