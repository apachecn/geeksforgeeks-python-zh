# Python–在 Tweepy

中的 API.retweets_of_me()

> 原文:[https://www . geesforgeks . org/python-API-retweets _ of _ me-in-tweepy/](https://www.geeksforgeeks.org/python-api-retweets_of_me-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.retweets_of_me()

Tweepy 模块中`API`类的 **`retweets_of_me()`** 方法用于获取已认证用户最近被他人转发的 20 条推文。

> **语法:**API . retwets _ of _ me(参数)
> 
> **参数:**
> 
> *   **自 _ 号:**只获取比指定号更新的状态。
> *   **最大标识:**仅获取早于或等于指定标识的状态。
> *   **计数:**待取状态数，默认值为 20。
> 
> **返回:**类状态的对象列表

**示例 1 :** 使用无任何参数的`retweets_of_me()`方法。

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

# fetching the retweets
statuses = api.retweets_of_me()

print(str(len(statuses)) + " number of statuses have been retweeted.")
```

**输出:**

```py
20 number of statuses have been retweeted.

```

**示例 2:** 使用带有计数参数的`retweets_of_me()`方法仅获取指定数量的转发。

```py
# screen name of the account to be fetched
screen_name = "geeksforgeeks"

# number of statuses to be fetched
count = 3

# fetching the retweets
statuses = api.retweets_of_me(count = count)

print(str(len(statuses)) + " number of statuses have been retweeted.")
```

**输出:**

```py
3 number of statuses have been retweeted.

```