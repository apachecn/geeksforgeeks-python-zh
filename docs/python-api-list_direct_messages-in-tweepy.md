# Python–Tweepy

中的 API.list_direct_messages()

> 原文:[https://www . geesforgeks . org/python-API-list _ direct _ messages-in-tweepy/](https://www.geeksforgeeks.org/python-api-list_direct_messages-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.list_direct_messages()

Tweepy 模块中`API`类的 **`list_direct_messages()`** 方法用于获取认证用户最近 30 天内的所有直接消息。

> **语法:** API.list_direct_messages(计数)
> 
> **参数:**
> 
> *   **计数:**要获取的直接消息数。
> *   **full_text :** 布尔值，指示是否应该返回消息的全文。
> 
> **返回:【DirectMessage 类的对象列表**

**例 1 :**

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

# fetching the direct messages
direct_messages = api.list_direct_messages()

# printing the timestamps
for direct_message in direct_messages:
    print(direct_message.created_timestamp)
```

**输出:**

```
1591868314610
1591868289514
1591868232626
1591867665376
1591867346546
1591867323014

```

**例 2 :** 统计最近 30 天的直邮数量。

```
# fetching the direct messages
direct_messages = api.list_direct_messages()

print(len(direct_messages))
```

**输出:**

```
6

```