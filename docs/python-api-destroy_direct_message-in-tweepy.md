# Python–Tweepy

中的 API.destroy_direct_message()

> 原文:[https://www . geesforgeks . org/python-API-destroy _ direct _ message-in-tweepy/](https://www.geeksforgeeks.org/python-api-destroy_direct_message-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.destroy_direct_message()

Tweepy 模块中`API`类的 **`destroy_direct_message()`** 方法用于删除直接消息。

> **语法:**API . destroy _ direct _ message(id)
> 
> **参数:**
> 
> *   **id :** 要销毁的直接报文的 id。
> 
> **返回:**无

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

# direct message ID
id = print("Before using the destroy_direct_message() object")
if api.get_direct_message(id):
    print("This direct message exists.")

# deleting the direct message
api.destroy_direct_message(id)

print("\nAfter using the destroy_direct_message() object")
try:
    api.get_direct_message(id)
except:
    print("This direct message no longer exists.")
```

**输出:**

```py
Before using the destroy_direct_message() object
This direct message exists.

After using the destroy_direct_message() object
This direct message no longer exists.

```

**示例 2 :** 试图删除不存在的直接消息会引发异常。

```py
# invalid direct message ID
id = 12345

# deleting the direct message
api.destroy_direct_message(id)
```

**输出:**

```py
    raise TweepError(error_msg, resp, api_code=api_error_code)
tweepy.error.TweepError: [{'code': 34, 'message': 'Sorry, that page does not exist.'}]

```