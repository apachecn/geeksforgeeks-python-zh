# Python | API.update_status()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-update _ status-in-tweepy-2/](https://www.geeksforgeeks.org/python-api-update_status-in-tweepy-2/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## update_status()

Tweepy 模块中`API`类的 **`API.update_status()`** 方法用于更新认证用户的当前状态，或者简单的说就是推文。

> **语法:** API.update_status(参数)
> 
> **参数:**
> 
> *   **状态:**推文/状态更新的文字。
> *   **in_reply_to_status_id :** 新推文正在回复的推文的 id。
> *   **attachment_url :** 这提供了一个作为推文附件的 url。
> *   **media _ id:**要与推文关联的 media _ id 列表。
> *   **可能敏感:**如果推文可能包含敏感数据，将其设置为真。
> *   **lat :** 推文的纬度。
> *   **长:**推文的经度。
> *   **place_id :** 推文的地点名称。
> *   **display_coordinates :** 如果必须显示推文的精确坐标，则将该值设置为 True。
> 
> **返回:**类状态的一个对象

**示例 1 :** 仅使用文本而不使用其他参数的`update_status()`方法。

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

# the text to be tweeted
status = "This is a tweet."

# posting the tweet
api.update_status(status)
```

**输出:**
![](img/3ced6a85c7d0b81b2033dbe58a523fc8.png)

**示例 2 :** 使用带 in_reply_to_status_id 参数的`update_status()`方法回复之前的推文。

```py
# the text to be tweeted
status = "This is a tweet is a reply."

# the ID of the tweet to be replied to
in_reply_to_status_id = ""

# posting the tweet
api.update_status(status, in_reply_to_status_id)
```

**输出:**
![](img/001a8b0c57da4d14836d792d32b3e89c.png)