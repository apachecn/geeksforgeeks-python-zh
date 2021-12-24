# Python–API . destroy _ status()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-destroy _ status-in-tweepy/](https://www.geeksforgeeks.org/python-api-destroy_status-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## 销毁 _ 状态()

Tweepy 模块中`API`类的 **`API.destroy_status()`** 方法用于删除授权用户的状态/推文。

> **语法:** API.destroy_status(id)
> 
> **参数:**
> 
> *   **id :** 状态的 id。
> 
> **返回:**类状态的一个对象

**示例 1 :** 删除以下推文:
![](img/3ced6a85c7d0b81b2033dbe58a523fc8.png)

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

# the ID of the status
ID = 

# deleting the status
api.destroy_status(ID)

# verifying if the status has 
# been deleted or not
try:
    api.get_status(ID)
except:
    print("The status has been successfully deleted.")
```

**输出:**

```
The status has been successfully deleted.
```

**例 2 :** 如果我们尝试删除别人的状态，会引发异常。尝试删除以下状态:
![](img/a82bc238ddc46ce23f061aa4e7106284.png)

```
# the ID of the status
ID = 1263493041769394178

# deleting the status
api.destroy_status(ID)
```

**输出:**

```
raise TweepError(error_msg, resp, api_code=api_error_code)
tweepy.error.TweepError: [{'code': 183, 'message': "You may not delete another user's status."}]

```