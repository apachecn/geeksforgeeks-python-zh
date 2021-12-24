# Python IMdbpy–人员信息集

> 原文:[https://www . geesforgeks . org/python-imdbpy-person-info-set/](https://www.geeksforgeeks.org/python-imdbpy-person-info-set/)

IMDb 数据库中有这个人的所有信息，例如获得什么奖项的人，传记等，但是为了检索它们，会出现问题，因为会有大量的网页，这可能既耗时又浪费带宽，尤其是如果你只对一小部分信息感兴趣的话。

如果我们只想获取特定的信息，我们可以通过向`get_person`方法传递一个可选的信息参数来获取它。为了获得 IMDb 人数据集的信息集，我们将使用`get_person_infoset`方法。

> **语法:**IMDB _ object . get _ person _ infoset()
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

# getting the person info set of data base
info = ia.get_person_infoset()

# printing the list 
for element in info:
    print(element)
```

**输出:**

```py
awards
biography
filmography
genres links
keywords links
main
news
official sites
other works
publicity

```