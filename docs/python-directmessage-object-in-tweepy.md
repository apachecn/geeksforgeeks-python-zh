# Python–Tweepy 中的 DirectMessage 对象

> 原文:[https://www . geesforgeks . org/python-direct message-object-in-tweepy/](https://www.geeksforgeeks.org/python-directmessage-object-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## 直接信息

Tweepy 模块中的 **`DirectMessage`** 对象包含一个地方的信息。

以下是 DirectMessage 对象中的属性列表:

> *   **Type:** The type of direct message.
> *   **id:** ID of the direct message.
> *   [T0】 created _ timestamp: 【T1] The timestamp when the direct message was created.
> *   **Message _ Creation:** Details of the content of the direct message, such as the sender's ID, text, media, etc.

**示例:**使用`get_direct_message()`方法获取直接消息。

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
id = 1271013844639313927

# fetching the direct message 
direct_message = api.get_direct_message(id) 

# printing the information
print("The type is : " + direct_message.type)
print("The id is : " + direct_message.id)
print("The created_timestamp is : " + direct_message.created_timestamp)

# inside message_create
print("The recipient_id is : " + direct_message.message_create['target']['recipient_id'])
print("The sender_id is : " + direct_message.message_create['sender_id'])
print("The source_app_id is : " + direct_message.message_create['source_app_id'])
print("The text is : " + str(direct_message.message_create['message_data']['text']))
print("The entities are : " + str(direct_message.message_create['message_data']['entities']))
print("The media attachment is : " + str(direct_message.message_create['message_data']['attachment']))
```

**输出:**

> 类型为:message _ create
> id 为:1271013844639313927
> created _ timestamp 为:1591868289514
> 收件人 _id 为:2344960135
> 发件人 _id 为:4801790172
> 来源 _app_id 为:3033300
> 文字为:https://t.co/wn8dK13pzf
> 实体为: media _ URL ':' https://ton . Twitter . com/1.1/ton/data/DM/1271013844639313927/1271013835181154304/gif1lwj 9 . png '，' media _ URL _ https ':' https://ton . Twitter . com/1.1/ton/data/DM/127101384639313927/127117