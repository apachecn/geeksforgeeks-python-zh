# Python–API . destroy _ mute()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-destroy _ mute-in-tweepy/](https://www.geeksforgeeks.org/python-api-destroy_mute-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.destroy_mute()

Tweepy 模块中`API`类的 **`destroy_mute()`** 方法用于将静音用户作为认证用户解除静音。

> **语法:**API . destroy _ mute(id/screen _ name/user _ id)
> 
> **参数:**仅使用 3 个选项之一:
> 
> *   **id :** 指定用户的 id 或屏幕名称。
> *   **user_id :** 指定用户的 id，当有效的用户 ID 也是有效的屏幕名称时，用于区分帐户。
> *   **screen_name :** 指定用户的屏幕名称，当有效的屏幕名称也是用户 id 时，用于区分帐户。
> 
> **返回:**用户类的对象

**示例 1 :** 考虑以下用户:
![](img/23fae3af0ca2ec4fa57d43db47e117b4.png)

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

# the screen name of the user
screen_name = "geeksforgeeks"

# un-muting the user
api.destroy_mute(screen_name)
```

**输出:**
![](img/e627ee1df16166d869599f2fe4cc99c5.png)

**示例 2 :** 通过`destroy_mute()`方法检查用户是否已取消静音。

```py
# ID of the user
id = 4802800777

print("Before using the destroy_mute() method : ")
if api.show_friendship(target_id = id)[0].muting == True:
    print("The user has been muted by the authenticated user.")
else:
    print("The user has not been muted by the authenticated user.")

# un-muting the user
api.destroy_mute(id)

print("\nAfter using the destroy_mute() method : ")
if api.show_friendship(target_id = id)[0].muting == True:
    print("The user has been muted by the authenticated user.")
else:
    print("The user has not  been muted by the authenticated user.")
```

**输出:**

```py
Before using the destroy_mute() method : 
The user has been muted by the authenticated user.

After using the destroy_mute() method : 
The user has not been muted by the authenticated user.

```