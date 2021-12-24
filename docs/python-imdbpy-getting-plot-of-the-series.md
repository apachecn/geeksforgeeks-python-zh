# Python IMDbPY–获取系列图

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-plot-of-the-series/](https://www.geeksforgeeks.org/python-imdbpy-getting-plot-of-the-series/)

在这篇文章中，我们将看到我们如何获得该系列的情节。情节是一系列事件，每个事件通过因果关系影响下一个事件。一个情节的因果事件可以被认为是由连接器“等等”连接起来的一系列事件。

> 为了做到这一点，我们必须做到以下几点–
> 
> 1.借助 get_movie 方法
> 2 获取系列详情。由于这个对象将作为字典，因此我们必须过滤对象
> 3。借助返回字典
> 4 的数据方法获取对象的主要数据。从字典中获取情节

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6077448"

# getting information
series = ia.get_movie(code)

# getting plot of the series
plot = series.data['plot']

# printing the object i.e name
print(series)

# print the plot
print(plot)
```

**输出:**

```
Sacred Games
['A link in their pasts leads an honest cop to a fugitive gang boss, whose cryptic warning spurs the officer on a quest to save Mumbai from cataclysm.', "Sartaj Singh, a Mumbai police officer, receives an anonymous phone call from a gangster who threatens to blow up the entire city. Amid the corrupt standards of Indian law enforcement begins a battle between a 'nobody' cop and ruthless gangster who perceives (sometimes) himself to be a God.::Cinema Theories", "Set in Mumbai, _Sacred Games_ (qv) delves into the city's intricate web of organized crime, corruption, politics and espionage that lie beneath India's economic renaissance. It is an epic masterwork of exceptional richness and power that interweaves the lives of the privileged, the famous, the wretched and the bloodthirsty.::ahmetkozan", 'Sartaj Singh a troubled police officer in Mumbai gets a call from gangster Ganesh Gaitonde who was missing for the last 16 years.He tells Sartaj that he has only 25 days to save Mumbai. Sartaj digs his past as to what made him a powerful gangster where he is helped by RNA officer Anjali Mathur.::alex.mjacko@gmail.com']
```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6468322"

# getting information
series = ia.get_movie(code)

# getting plot of the series
plot = series.data['plot']

# printing the object i.e name
print(series)

# print the plot
print(plot)
```

**输出:**

```
Money Heist
['An unusual group of robbers attempt to carry out the most perfect robbery in Spanish history - stealing 2.4 billion euros from the Royal Mint of Spain.']
```