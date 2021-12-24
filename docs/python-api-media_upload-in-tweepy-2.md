# Python–API . media _ upload()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-media _ upload-in-tweepy-2/](https://www.geeksforgeeks.org/python-api-media_upload-in-tweepy-2/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.media_upload()

Tweepy 模块中 API 类的 **media_upload()** 方法用于将一个媒体对象上传到 Twitter。

> **语法:** API.media_upload(文件名，文件)
> 参数:
> 
> *   **文件名:**要上传的媒体文件的路径。
> *   **文件:**要上传的文件对象。
> 
> **返回:**媒体类的对象

**例 1 :**

## 蟒蛇 3

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

# the name of the media file
filename = "gfg.png"

# upload the file
media = api.media_upload(filename)

# printing the information
print("The media ID is : " + media.media_id_string)
print("The size of the file is : " + str(media.size) + " bytes")
```

**输出:**

```py
The media ID is : 1270554007983910912
The size of the file is : 3346 bytes
```

**示例 2 :** 使用 media_upload()方法查找图像文件的尺寸。

## 蟒蛇 3

```py
# the name of the media file
filename = "gfg.png"

# upload the file
media = api.media_upload(filename)

# printing the dimensions
print("The width is : " + str(media.image['w']) + " pixels.")
print("The height is : " + str(media.image['h']) + " pixels.")
```

**输出:**

```py
The width is : 225 pixels.
The height is : 225 pixels.
```