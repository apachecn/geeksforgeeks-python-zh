# Python–API . get _ status()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-get _ status-in-tweepy/](https://www.geeksforgeeks.org/python-api-get_status-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## get_status()

Tweepy 模块中`API`类的 **`API.get_status()`** 方法用于获取状态/推文。

> **语法:** API.get_status(参数)
> 
> **参数:**
> 
> *   **id :** 状态的 id。
> *   **trim_user :** 一个布尔值，指示是否应该提供用户标识，而不是完整的用户对象。默认值为假。
> 
> **返回:**类状态的一个对象

**示例 1 :** 考虑以下推文:
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

# obtaining the status
status = api.get_status(ID)

# printing the text of the status
print("The text of the status is : " + status.text)
```

**输出:**

```
The text of the tweet is : This is a tweet.
```

**例 2 :** 考虑以下推文:
![](img/8dbee9eb8e96767186941174843985e1.png)
获取上述推文的网名、回复数、转发数。

```
# the ID of the status
ID = 1265569813281280006

# obtaining the status
status = api.get_status(ID)

# printing the text of the status
print("The text of the status is : \n\n" + status.text)

# printing the screen name
print("\nThe status was posted by : " + status.user.screen_name)

# printing the number of likes
print("The status has been liked " + str(status.favorite_count) + " number of times.")

# printing the number of retweets
print("The status has been retweeted " + str(status.retweet_count) + " number of times.")
```

**输出:**

```
The text of the status is : 

Apart from coding, what GEEKS are doing in quarantine?

Reply us...

#Quarantine #QuarantineLife #coding #programming

The status was posted by : geeksforgeeks
The status has been liked 25 number of times.
The status has been retweeted 3 number of times.

```