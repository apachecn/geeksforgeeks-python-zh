# Python IMDbPY–获取系列每一季的每集年份

> 原文:[https://www . geeksforgeeks . org/python-imdbpy-get-每季每集-年度最佳剧集/](https://www.geeksforgeeks.org/python-imdbpy-getting-each-episode-year-of-each-season-of-the-series/)

在本文中，我们将看到如何从剧集信息集中获取该系列每一季每集的年份。每个系列都有季节，每个季节都有多集，即每集是季节的子集，季节是系列的子集。我们通过向剧集添加剧集信息集来获取剧集详细信息

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。使用
> 3 的更新方法为其添加剧集信息集。由于这个对象将作为字典，因此我们必须过滤对象
> 4。借助返回字典
> 5 的数据方法获取对象的主要数据。剧集的每一个键指的是季节，季节的每一个键指的是剧集
> 6。打印每集的年份

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

        # getting year of episode
        year = episodes[i][j]['year']

        # printing title
        print(" Ep " + str(j) + " year : " + str(year))        
```

**输出:**

```
Mirzapur
=========
Season1
 Ep 1 year : 2020
 Ep 2 year : 2018
 Ep 3 year : 2018
 Ep 4 year : 2018
 Ep 5 year : 2018
 Ep 6 year : 2018
 Ep 7 year : 2018
 Ep 8 year : 2018
 Ep 9 year : 2018

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

        # getting year of episode
        year = episodes[i][j]['year']

        # printing title
        print(" Ep " + str(j) + " year : " + str(year))        
```

**输出:**

```
Sacred Games
=========
Season2
 Ep 1 year : 2019
 Ep 2 year : 2019
 Ep 3 year : 2019
 Ep 4 year : 2019
 Ep 5 year : 2019
 Ep 6 year : 2019
 Ep 7 year : 2019
 Ep 8 year : 2019
Season1
 Ep 1 year : 2018
 Ep 2 year : 2018
 Ep 3 year : 2018
 Ep 4 year : 2018
 Ep 5 year : 2018
 Ep 6 year : 2018
 Ep 7 year : 2018
 Ep 8 year : 2018
```