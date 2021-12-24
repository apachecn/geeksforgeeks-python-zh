# Python–API . media _ upload()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-media _ upload-in-tweepy/](https://www.geeksforgeeks.org/python-api-media_upload-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## 媒体 _ 上传()

Tweepy 模块中`API`类的 **`API.media_upload()`** 方法用于通过媒体或者简单的说就是推文更新认证用户的当前状态。

> **语法:** API.media_upload(参数)
> 
> **参数:**
> 
> *   **文件名:**要上传的文件的名称。
> *   **状态:**推文/状态更新的文字。
> *   **in_reply_to_status_id :** 新推文正在回复的推文的 id。
> *   **attachment_url :** 这提供了一个作为推文附件的 url。
> *   **media _ id:**要与推文关联的 media _ id 列表。
> *   **可能敏感:**如果推文可能包含敏感数据，将其设置为真。
> *   **lat :** 推文的纬度。
> *   **长:**推文的经度。
> *   **place_id :** 推文的地点名称。
> *   **display_coordinates :** 如果必须显示推文的精确坐标，则将该值设置为 True。
> *   **文件:**一个文件对象，在没有给定文件名的情况下被访问。
> 
> **返回:**类状态的一个对象

**例 1 :** 发布一条推文，文件如下:
![](img/82950c201c2d981b37b6fbed0f843420.png)

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
status = "This is a media upload."

# the path of the media to be uploaded
filename = "gfg.png"

# posting the tweet
api.update_with_media(filename, status)
```

**输出:**
![](img/5680188515a423f9d80533bbe53e821e.png)

**示例 2 :** 使用带 in_reply_to_status_id 参数的`media_upload()`方法回复之前的推文，使用以下媒体:
![](img/faf013d6aaf62d0340f0acfa7d1c5a09.png)

```py
# the text to be tweeted
status = "This is a tweet is a reply."

# the ID of the tweet to be replied to
in_reply_to_status_id = ""

# the path of the media to be uploaded
filename = "gfg.png"

# posting the tweet
api.update_with_media(filename, status, in_reply_to_status_id = in_reply_to_status_id)
```

**输出:**
![](img/fde784b12989813fe0e0c30595b65c19.png)