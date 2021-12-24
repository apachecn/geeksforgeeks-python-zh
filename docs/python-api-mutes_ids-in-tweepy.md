# Python–Tweepy

中的 API.mutes_ids()

> 原文:[https://www . geesforgeks . org/python-API-mutes _ ids-in-tweepy/](https://www.geeksforgeeks.org/python-api-mutes_ids-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.mutes_ids()

Tweepy 模块中`API`类的 **`mutes_ids()`** 方法用于获取被认证用户阻止的用户的所有用户 id 列表。

> **语法:** API.mutes_ids()
> 
> **参数:**无
> 
> **返回:**整数列表

**示例 1 :** 使用`mutes_ids()`方法查找认证用户静音的用户数量。

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

# getting the muted users
muted_users = api.mutes_ids()

# printing the number of muted users
print(len(muted_users))
```

**输出:**

```
2
```

**示例 2 :** 使用`mutes_ids()`方法查找被认证用户静音的所有用户的用户标识。

```
# getting the muted users
muted_users = api.mutes_ids()

# printing the user IDs of the muted users
for IDs in muted_users:
    print(IDs)
```

**输出:**

```
4802800777
37222058

```