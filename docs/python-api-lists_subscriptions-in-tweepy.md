# Python–API . list _ subscriptions()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-list _ subscriptions-in-tweepy/](https://www.geeksforgeeks.org/python-api-lists_subscriptions-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.lists _ subscriptions()

Tweepy 模块中`API`类的 **`lists_subscriptions()`** 方法用于获取指定用户订阅的所有列表。

> **语法:**API . list _ subscriptions(参数)
> 
> **参数:**
> 
> *   **用户 _id :** 用户的 id。
> *   **屏幕名称:**用户的屏幕名称。
> *   **计数:**要获取的列表数。
> 
> 如果没有参数，将获取经过身份验证的用户的列表。
> 
> **返回:**类列表的对象列表

**示例 1 :** 使用无任何参数的`lists_subscriptions()`方法。

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

# fetching all the lists
list = api.lists_subscriptions()

# counting the number of lists
print("The authenticated user has been subscribed to " + str(len(list)) + " list(s).")
```

**输出:**

```
The authenticated user has been subscribed to 7 list(s).

```

**示例 2 :** 获取另一个用户的列表。

```
# the screen name user
screen_name = "geeksforgeeks"

# fetching all the lists
api.lists_subscriptions(screen_name)

# counting the number of lists
print("The user " + screen_name + " has been subscribed to " + str(len(list)) + " list(s).")
```

**输出:**

```
The user geeksforgeeks has been lists_subscribed to 0 list(s).

```