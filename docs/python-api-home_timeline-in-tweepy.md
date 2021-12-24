# Python–API . home _ timeline()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-home _ timeline-in-tweepy/](https://www.geeksforgeeks.org/python-api-home_timeline-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.home_timeline()

Tweepy 模块中`API`类的 **`home_timeline()`** 方法用于获取认证用户和该用户好友发布的 20 个最新状态，包括转发。这相当于网络上的/时间轴/主页。

> **语法:** API.home_timeline(参数)
> 
> **参数:**
> 
> *   **自 _ 号:**只获取比指定号更新的状态。
> *   **最大标识:**仅获取早于或等于指定标识的状态。
> *   **计数:**待取状态数，默认值为 20。
> 
> **返回:**类状态的对象列表

**示例 1 :** 使用无任何参数的`home_timeline()`方法。

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

# fetching the statuses
statuses = api.home_timeline()

# printing the screen names of each status
for status in statuses:
    print(status.user.screen_name)
```

**输出:**

```py
republic
AapGhumaKeLeLo_
vijaita
ABPNews
1911_1913_BakUp
BBCPolitics
SwarajyaMag
WIONews
YourAnonNews
thehill
AP
TimesNow
krystalball
People4Bernie
Holbornlolz
RealSaavedra
BenjaminPDixon
BJP4Haryana
BuzzFeed
MixedRaita

```

**示例 2:** 使用带有计数参数的`home_timeline()`方法仅获取指定数量的状态。

```py
# number of statuses to be fetched
count = 5

# fetching the statuses
statuses = api.home_timeline(count = count)

# printing the screen names of each status
for status in statuses:
    print(status.user.screen_name)
```

**输出:**

```py
ANI
alexkotch
chrislongview
CNN
CGTNOfficial

```