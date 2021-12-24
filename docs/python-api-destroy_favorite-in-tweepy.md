# Python–API . destroy _ 收藏夹()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-destroy _ favorite-in-tweepy/](https://www.geeksforgeeks.org/python-api-destroy_favorite-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.destroy _ 收藏夹()

Tweepy 模块中`API`类的 **`destroy_favorite()`** 方法用于取消身份验证用户的身份。

> **语法:**API . destroy _ 收藏夹(id)
> 
> **参数:**
> 
> *   **id :** 指定状态的 id。
> 
> **返回:**类状态的对象

**例 1 :** 考虑以下状态:
![](img/1fb4828bd4cda6f8422f597113d025a0.png)

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

# ID of the status
id = 1268080321590935553

# un-liking the status
api.destroy_favorite(id)
```

**输出:**
![](img/693b7b16d364e6e27192ab1f1c84ad28.png)

**示例 2 :** 通过`destroy_favorite()`方法检查状态是否不喜欢。

```
# ID of the status
id = 1267740427676942337

print("Before using the destroy_favorite() method : ")
if api.get_status(id).favorited == True:
    print("The status has been liked by the authenticated user.")
else:
    print("The status has not been liked by the authenticated user.")

# un-liking the status
api.destroy_favorite(id)

print("\nAfter using the destroy_favorite() method : ")
if api.get_status(id).favorited == True:
    print("The status has been liked by the authenticated user.")
else:
    print("The status has not been liked by the authenticated user.")
```

**输出:**

```
Before using the destroy_favorite() method : 
The status has been liked by the authenticated user.

After using the destroy_favorite() method : 
The status has not been liked by the authenticated user.

```