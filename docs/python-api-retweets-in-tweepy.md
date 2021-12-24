# Python–Tweepy 中的 API.retweets()

> 原文:[https://www . geesforgeks . org/python-API-retweets-in-tweepy/](https://www.geeksforgeeks.org/python-api-retweets-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## retweets()

Tweepy 模块中`API`类的 **`API.retweets()`** 方法用于返回推文的转发列表。

> **语法:** API.retweets(参数)
> 
> **参数:**
> 
> *   **id :** 必须转发的推文的 id。
> *   **计数:**要检索的转发数。
> 
> **返回:**类状态的对象列表

**示例 1 :** 转发以下推文的用户列表:
![](img/0a3eeae6a3b0d11063cb3eb292b110ea.png)

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

# the ID of the tweet
ID = 1265889240300257280

# getting the retweeters
retweets_list = api.retweets(ID)

# printing the screen names of the retweeters
for retweet in retweets_list:
    print(retweet.user.screen_name)
```

**输出:**

```
harshitabambure
codedailybot
UVahalkar
codedailybot
ProjectLearn_io
codedailybot
ryokugyu_
AaronCuddeback

```

strong >示例 2:使用带 count 参数的`retweets()`方法只获取一定数量的转发。只打印以下推文的 3 个转发者的网名:
![](img/3c7dd012a6d2b59fbe82577fc536abc9.png)

```
# the ID of the tweet
ID = 1263387365051183107

# number to retweets to be retrieved
count = 3

# getting the retweeters
retweets_list = api.retweets(ID, count)

# printing the screen names of the retweeters
for retweet in retweets_list:
    print(retweet.user.screen_name)
```

**输出:**

```
murali_ch
sushmitaraj13
rgsharma_me

```