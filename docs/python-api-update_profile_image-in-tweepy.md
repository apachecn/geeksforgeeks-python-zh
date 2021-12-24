# Python–Tweepy

中的 API.update_profile_image()

> 原文:[https://www . geesforgeks . org/python-API-update _ profile _ image-in-tweepy/](https://www.geeksforgeeks.org/python-api-update_profile_image-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.update_profile_image()

Tweepy 模块中`API`类的 **`update_profile_image()`** 方法用于更新认证用户的个人资料图像。

> **语法:** API.update_profile_image(文件名)
> 
> **参数:**
> 
> *   **文件名:**图像文件的本地路径。
> 
> **返回:**用户类的对象

**例 1 :** 用下图更新简介图片:
![](img/d093f13d023b55312587c75db80e6934.png)

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

# the file path
filename = "sunflower.jpg"

# updating the profile picture
api.update_profile_image(filename)
```

**输出:**
![](img/8dcd09560f51ffdd6af5ca6d59893b64.png)

**示例 2 :** 尝试上传 GIF、JPG 或 PNG 以外的文件将会创建一个异常。

```py
# the file path
filename = "sunflower.mp3"

# updating the profile picture
api.update_profile_image(filename)
```

**输出:**

```py
    raise TweepError('Invalid file type for image: %s' % file_type)
tweepy.error.TweepError: Invalid file type for image: None

```