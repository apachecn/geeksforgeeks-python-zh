# Python–API . send _ direct _ message()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-send _ direct _ message-in-tweepy/](https://www.geeksforgeeks.org/python-api-send_direct_message-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.send_direct_message()

Tweepy 模块中`API`类的 **`send_direct_message()`** 方法用于作为认证用户发送直接消息。

> **语法:** API.send_direct_message(参数)
> 
> **参数:**
> 
> *   **收件人 _id :** 收件人的 id。
> *   **文本:**直接消息的文本。
> *   **附件 _ 类型:**要发送的附件介质或位置。
> *   **附件 _ 媒体 _id :** 要发送的附件媒体的 id。
> 
> **返回:**一个 DirectMessage 类的对象

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

# ID of the recipient
recipient_id = 

# text to be sent
text = "This is a Direct Message."

# sending the direct message
direct_message = api.send_direct_message(recipient_id, text)

# printing the text of the sent direct message
print(direct_message.message_create['message_data']['text'])
```

**输出:**

```
This is a Direct Message.

```

**示例 2 :** 发送带有以下媒体附件的直接消息:
![](img/63ac17ed0ded2daedad1649abd6f7deb.png)

```
# ID of the recipient
recipient_id = 

# text to be sent
text = "This is a Direct Message."

# the ID of the media
attachment_media_id = 

# sending the direct message
direct_messages = api.send_direct_message(recipient_id, text,
                    attachment_media_id = attachment_media_id)
```

**输出:**
![](img/0457fb6282476f19af5f3dbad63c6a70.png)