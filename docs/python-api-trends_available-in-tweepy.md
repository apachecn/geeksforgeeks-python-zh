# Python–API . trends _ available()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-trends _ available-in-tweepy/](https://www.geeksforgeeks.org/python-api-trends_available-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.trends_available()

Tweepy 模块中`API`类的 **`trends_available()`** 方法用于获取 Twitter 有趋势话题信息的位置。

> **语法:** API.trends_available()
> 
> **参数:**无
> 
> **返回:【JSON 类的一个对象**

**例 1 :**

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

# fetching the trends
trends = api.trends_available()

print("The number of locations available are : " + str(len(trends)))
```

**输出:**

```
The number of locations available are : 467

```

**例 2 :**

```
# fetching the trends
trends = api.trends_available()

print("Some of the locations are : ")
for i in range(0, 200, 20):
    print("Place : " + trends[i]['name'] +
          ", Country : " + trends[i]['country'])
```

**输出:**

```
Some of the locations are : 
Place : Worldwide, Country : 
Place : Leeds, Country : United Kingdom
Place : Mexico City, Country : Mexico
Place : Mendoza, Country : Argentina
Place : Belo Horizonte, Country : Brazil
Place : Lodz, Country : Poland
Place : Dortmund, Country : Germany
Place : Utrecht, Country : Netherlands
Place : Oslo, Country : Norway
Place : Palembang, Country : Indonesia

```