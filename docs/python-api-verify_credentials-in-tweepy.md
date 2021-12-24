# Python–API . verify _ credentials()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-verify _ credentials-in-tweepy/](https://www.geeksforgeeks.org/python-api-verify_credentials-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.verify_credentials()

Tweepy 模块中`API`类的 **`verify_credentials()`** 方法用于验证提供的用户凭证是否有效。

> **语法:**API . verify _ credentials(include _ entities，skip_status，include_email)
> 
> **参数:**
> 
> *   **include_entities :** 实体节点设置为 false 时不包含，默认为 true。
> *   **skip_status :** 状态将不包含在返回的用户对象中，默认为 false。
> *   **include_email :** email 将在用户对象中作为字符串返回。
> 
> **返回:**用户类的对象

**例 1 :**

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

if api.verify_credentials() == False:
    print("The user credentials are invalid.")
else:
    print("The user credentials are valid.")
```

**输出:**

```py
The user credentials are valid.

```

**示例 2 :** 获取验证用户。

```py
# fetching the verified user
user = api.verify_credentials()

# printing the information
print("The user has " + str(user.followers_count) + " followers.")
print("The user has " + str(user.friends_count) + " friends.")
```

**输出:**

```py
The user has 44 followers.
The user has 1016 friends.

```