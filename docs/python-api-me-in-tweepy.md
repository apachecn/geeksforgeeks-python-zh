# Tweepy 中的 Python–API . me()

> 原文:[https://www.geeksforgeeks.org/python-api-me-in-tweepy/](https://www.geeksforgeeks.org/python-api-me-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## 我()

Tweepy 模块中`API`类的 **`API.me()`** 方法用于获取认证用户的信息。

> **语法:** API.me()
> 
> **参数:**无
> 
> **返回:**用户类的一个对象

**示例 1 :** 获取经过身份验证的用户的名称。在这里，我们假设经过身份验证的用户是 GeeksforGeeks twitter 帐户。

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

# getting the authenticated user's information
user = api.me()

# printing the name of the user
print("The authenticated user's name is : " + user.name)
```

**输出:**

```
The authenticated user's name is : GeeksforGeeks
```

**示例 2 :** 获取认证用户的屏幕名称。在这里，我们假设经过身份验证的用户是 GeeksforGeeks twitter 帐户。

```
# getting the authenticated user's information
user = api.me()

# printing the screen name of the user
print("The authenticated user's screen name is : " + user.screen_name)
```

**输出:**

```
The authenticated user's screen name is : geeksforgeeks
```

**例 3 :** 获取认证用户的 ID。在这里，我们假设经过身份验证的用户是 GeeksforGeeks twitter 帐户。

```
# getting the authenticated user's information
user = api.me()

# printing the ID of the user
print("The authenticated user's ID is : " + str(user.id))
```

**输出:**

```
The authenticated user's ID is : 57741058
```

**示例 4 :** 获取认证用户的位置。在这里，我们假设经过身份验证的用户是 GeeksforGeeks twitter 帐户。

```
# getting the authenticated user's information
user = api.me()

# printing the location of the user
print("The authenticated user's location is : " + user.location)
```

**输出:**

```
The authenticated user's location is : India
```