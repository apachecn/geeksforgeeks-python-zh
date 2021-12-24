# Python–Tweepy 中的 API.get_user()

> 原文:[https://www . geesforgeks . org/python-API-get _ user-in-tweepy/](https://www.geeksforgeeks.org/python-api-get_user-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## get_user()

Tweepy 模块中 API 类的 **`get_user()`** 方法用于获取指定用户的信息。

> **语法:**API . get _ user(id/user _ id/screen _ name)
> 
> **参数:**仅使用 3 个选项之一:
> **id :** 指定用户的 id 或屏幕名称
> **user_id :** 指定用户的 id，当有效用户 ID 也是有效屏幕名称时用于区分账户
> **screen_name :** 指定用户的屏幕名称，当有效屏幕名称也是用户 ID 时用于区分账户
> 
> **返回:**用户类的一个对象

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

# using get_user with id
_id = "103770785"
user = api.get_user(_id)

# printing the name of the user
print("The id " + _id +
      " corresponds to the user with the name : " +
      user.name)
```

**输出:**

```py
The id 103770785 corresponds to the user with the name : Twitter India

```

**例 2 :** 有时候两个不同用户的`user_id`和`screen_name`可能是一样的，所以我们需要明确提到的不是`user_id`就是`screen_name`。

```py
# using get_user with user_id
user_id = "57741058"
user = api.get_user(user_id)

# printing the name of the user
print("The user id " + user_id +
      " corresponds to the user with the name : " +
      user.name)

# using get_user with screen_name
screen_name = "geeksforgeeks"
user = api.get_user(screen_name)

# printing the name of the user
print("\nThe screen name " + screen_name +
      " corresponds to the user with the name : " +
      user.name)
```

**输出:**

```py
The user id 57741058 corresponds to the user with the name : GeeksforGeeks

The screen name geeksforgeeks corresponds to the user with the name : GeeksforGeeks

```