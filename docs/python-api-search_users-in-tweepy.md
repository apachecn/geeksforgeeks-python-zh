# Python–API . search _ users()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-search _ users-in-tweepy/](https://www.geeksforgeeks.org/python-api-search_users-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.search_users()

Tweepy 模块中`API`类的 **`search_users()`** 方法用于基于查询运行搜索，并获取与该查询匹配的用户，类似于“查找人员”按钮。

> **语法:** API.search_users(q，count)
> 
> **参数:**
> **q :** 要搜索的文本
> **计数:**指定要检索的用户数，不能大于 20，默认值为 20
> 
> **返回:**用户类的对象列表

**示例 1 :** 默认情况下`search_users()`检索 20 个用户。

```py
# import the module
import tweepy

# assign the values accordingly
consumer_key = ""
consumer_secret = ""
access_token = ""
access_token_secret = ""

# authorization of consumer key and consumer secret
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)

# set access to user's access key and access secret 
auth.set_access_token(access_token, access_token_secret)

# calling the api 
api = tweepy.API(auth)

# the query to be searched
q = "geeks"

# search the query
users = api.search_users(q)

# print the users retrieved
for user in users:
    print(user.screen_name)
```

**输出:**

```py
GeeksOUT
GWOBorg
GeeksOfColor
geeksaresexy
WeatherGeeks
CoachingGeeks
DealsForGeeks
TwinCitiesGeeks
RetroGameGeeks
BuddhistGeeks
KevinGeeksOut
mcrgirlgeeks
AirplaneGeeks
AirlineGeeks
geeks_3d
GeeksGamersCom
javacodegeeks
wearemoviegeeks
The_GWW
GeeksRoom

```

**示例 2:** 使用 count 参数检索不到 20 个用户。

```py
# the query to be searched
q = "geeksforgeeks"

# number of users to be retrieved
count = 3

# search the query
users = api.search_users(q, count)

# print the users retrieved
for user in users:
    print(user.screen_name)
```

**输出:**

```py
geeksforgeeks
gfgvideos
gfg_reader

```