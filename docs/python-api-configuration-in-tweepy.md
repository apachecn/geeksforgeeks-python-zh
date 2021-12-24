# Python–Tweepy 中的 API.configuration()

> 原文:[https://www . geesforgeks . org/python-API-configuration-in-tweepy/](https://www.geeksforgeeks.org/python-api-configuration-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.configuration()

Tweepy 模块中`API`类的 **`configuration()`** 方法用于获取 Twitter 使用的当前配置。

> **语法:** API.configuration()
> 
> **参数:**无
> 
> **返回:**类字典的一个对象

**示例:**

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

# getting the configuration
configuration = api.configuration()

# printing the information
for key, value in configuration.items():
    print(key  + " : " + str(value), end = "\n\n")
```

**输出:**

> dm_text_character_limit : 10000
> 
> 字符 _ 保留 _ 每媒体:24
> 
> max_media_per_upload : 1
> 
> non _ username _ path:[' about '，' account '，' activity '，' all '，' notifications '，' anywhere '，' api_rules '，' api_terms '，' apps '，' auth '，'徽章'，' blog '，' business '，' button '，'联系人'，'设备'，' direct_messages '，'下载'，'下载'，' edit _ notifications '，' faq '，'收藏夹'，' find_sources '，' find_users '，' followers '，' following '，' friend_request '，' friend '，'
> 
> photo_size_limit : 3145728
> 
> photo _ size:{ ' thumb ':{ ' h ':150，' resize': 'crop '，' w': 150}，' small': {'h': 480，' resize': 'fit '，' w': 340}，' medium': {'h': 1200，' resize': 'fit '，' w': 600}，' large': {'h': 2048，' resize': 'fit '，' w': 1024}}
> 
> 短 url 长度:23
> 
> short _ URL _ long _ https:23