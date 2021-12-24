# Python–Tweepy 中的 API.update_profile()

> 原文:[https://www . geesforgeks . org/python-API-update _ profile-in-tweepy/](https://www.geeksforgeeks.org/python-api-update_profile-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.update_profile()

Tweepy 模块中`API`类的 **`update_profile()`** 方法用于更新认证用户的档案。

> **语法:** API.update_profile(文件名)
> 
> **参数:**
> 
> *   **名称:**配置文件的名称，最多 20 个字符。
> *   **网址:**链接的网址，最多 100 个字符。
> *   **位置:**用户的位置，最多 30 个字符。
> *   **描述:**简介描述，最多 10 个字符。
> 
> **返回:**用户类的对象

**示例 1 :** 更新配置文件的名称。

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

# the profile name to be updated
name = "Geeky Yash"

# updating the background picture
api.update_profile(name)
```

**输出:**
![](img/8cf0aa73b473968e3f6cb383c795c846.png)

**示例 2 :** 更新配置文件的位置。

```
# the location to be updated
location = "India"

# updating the background picture
api.update_profile(location = location)
```

**输出:**
![](img/5d927e07dd731fb83e8287f26b419057.png)