# Python–Tweepy

中的 API . un treet()

> 原文:[https://www . geesforgeks . org/python-API-un reteet-in-tweepy/](https://www.geeksforgeeks.org/python-api-unretweet-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## 取消推文()

Tweepy 模块中`API`类的 **`API.unretweet()`** 方法用于取消转发已转发的推文。

> **语法:**API . un tweet(id)
> 
> **参数:**
> 
> *   **id :** 必须取消转发的推文的 id。
> 
> **返回:**类状态的一个对象

**示例 1 :** 取消转发自己转发的 tween。取消发布以下推文:
![](img/d2d977262cd83510f71c13f6dee35878.png)

```
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

# the ID of the tweet to be un-retweeted
ID = 

# un-retweeting the tweet
api.unretweet(ID)
```

**输出:**
![](img/3ced6a85c7d0b81b2033dbe58a523fc8.png)

**示例 2 :** 取消转发其他账户转发的推文。取消转发以下推文:
![](img/29a173210682e840baba63a15eb2f098.png)

获取上述推文的网名、回复数和转发数。

```
# the ID of the tweet to be un-retweeted
ID = 1263493041769394178

# un-retweeting the tweet
api.unretweet(ID)
```

**输出:**
![](img/a82bc238ddc46ce23f061aa4e7106284.png)