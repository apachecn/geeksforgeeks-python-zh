# Python–API . destroy _ friendly()in Tweepy

> 原文:[https://www . geesforgeks . org/python-API-destroy _ friendly-in-tweepy/](https://www.geeksforgeeks.org/python-api-destroy_friendship-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.destroy _ friendship()

Tweepy 模块中`API`类的 **`destroy_friendship()`** 方法被用来破坏认证用户和目标用户之间的友谊(unfollow)。

> **语法:**API . destroy _ friendly(id/user _ id/screen _ name)
> 
> **参数:**仅使用 3 个选项之一:
> 
> *   **id :** 指定用户的 id 或屏幕名称。
> *   **user_id :** 指定用户的 id，当有效的用户 ID 也是有效的屏幕名称时，用于区分帐户。
> *   **screen_name :** 指定用户的屏幕名称，当有效的屏幕名称也是用户 id 时，用于区分帐户。
> 
> **返回:**用户类的一个对象

**例 1 :** 利用网名破坏友谊。考虑以下账户:
![](img/e7cf1ad934584233b1453c35e4386fcb.png)

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

# screen name of the account to be unfollowed
screen_name = "geeksforgeeks"

# destroying the friendship
api.destroy_friendship(screen_name)
```

**输出:**
![](img/a67cc9fb38edfd1453359824a88d14fd.png)

**例 2 :** 利用用户 id 破坏友谊。考虑以下账户:
![](img/8743affc0a5c89f3ea9b5558f1d3a9ea.png)

```
# user id of the account to be unfollowed
user_id = 103770785

# destroying the friendship
api.destroy_friendship(user_id)
```

**输出:**

```
The user id 57741058 corresponds to the user with the name : GeeksforGeeks

The screen name geeksforgeeks corresponds to the user with the name : GeeksforGeeks

```

**输出:**
![](img/8c3e11832dd86970de6b8f8b388da378.png)