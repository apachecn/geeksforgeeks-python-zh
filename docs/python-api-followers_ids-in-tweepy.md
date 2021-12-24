# Python–Tweepy

中的 API.followers_ids()

> 原文:[https://www . geesforgeks . org/python-API-followers _ ids-in-tweepy/](https://www.geeksforgeeks.org/python-api-followers_ids-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.followers_ids()

Tweepy 模块中`API`类的 **`followers_ids()`** 方法用于获取用户所有关注者的 id。

> **语法:**API . followers _ ids(id/user _ id/screen _ name)
> 
> **参数:**仅使用 3 个选项之一:
> 
> *   **id :** 指定用户的 id 或屏幕名称。
> *   **user_id :** 指定用户的 id，当有效的用户 ID 也是有效的屏幕名称时，用于区分帐户。
> *   **screen_name :** 指定用户的屏幕名称，当有效的屏幕名称也是用户 id 时，用于区分帐户。
> 
> **返回:**整数列表

**例 1 :** 使用`followers_ids()`方法，屏幕名称。

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

# screen name of the user
screen_name = "CoursesGfG"

# getting the followers list
followers = api.followers_ids(screen_name)

print(screen_name + " has " + str(len(followers)) + " followers.")
```

**输出:**

```
CoursesGfG has 198 followers.

```

**示例 2 :** 使用带用户标识的`followers_ids()`方法。

```
# user ID of the user
user_id = 1037141442

# getting the followers list
followers = api.followers_ids(user_id)

print(api.get_user(user_id).screen_name + " has " + str(len(followers)) + " followers.")
```

**输出:**

```
GeeksQuiz has 3449 followers.

```