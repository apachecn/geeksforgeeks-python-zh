# Python–API . get _ direct _ message()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-get _ direct _ message-in-tweepy/](https://www.geeksforgeeks.org/python-api-get_direct_message-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.get_direct_message()

Tweepy 模块中`API`类的 **`get_direct_message()`** 方法用于作为认证用户获取直接消息。

> **语法:** API.get_direct_message(id，全文)
> 
> **参数:**
> 
> *   **id :** 直接消息的 id。
> *   **full_text :** 布尔值，指示是否应该返回消息的全文。
> 
> **返回:**一个 DirectMessage 类的对象

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

# ID of the direct message
id = 

# fetching the direct message
direct_message = api.get_direct_message(id)

print(direct_message.message_create['message_data']['text'])
```

**输出:**

```py
This is a Direct Message.

```

**例 2:**ID 无效时引发异常。

```py
# invalid ID of the direct message
id = 12345

# fetching the direct message
direct_message = api.get_direct_message(id)
```

**输出:**

```py
    raise TweepError(error_msg, resp, api_code=api_error_code)
tweepy.error.TweepError: [{'code': 34, 'message': 'Sorry, that page does not exist.'}]

```