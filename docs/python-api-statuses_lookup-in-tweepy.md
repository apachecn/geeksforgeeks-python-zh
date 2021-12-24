# Python–Tweepy 中的 API.statuses _ lookup()

> 原文:[https://www . geesforgeks . org/python-API-States _ lookup-in-tweepy/](https://www.geeksforgeeks.org/python-api-statuses_lookup-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.statuses _ lookup()

Tweepy 模块中`API`类的 **`statuses_lookup()`** 方法用于获取状态标识指定的状态，最多 100 个。

> **语法:**API . States _ lookup(参数)
> 
> **参数:**
> 
> *   **id_ :** 要获取的推文 id 列表，最多 100 个
> *   **trim_user :** 一个布尔值，表示是否应该提供用户 id，而不是完整的用户对象，默认值为 False。
> 
> **返回:**类状态的对象列表

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

# list of status IDs to be fetched 
id_ = [1266978261701210112, 1266735261012111360, 1266342841648898049]

# fetching the statuses
statuses = api.statuses_lookup(id_)

# printing the statuses
for status in statuses:
    print("The status " + str(status.id) + " is posted by " + status.user.screen_name)
    print("This status says : \n\n" + status.text, end = "\n\n")
```

**输出:**

```
The status 1266978261701210112 is posted by geeksforgeeks
This status says : 

Avoid errors, not client calls
.
Geeks, Keep this going...
.
#sundayvibes #programming #programmingmemes #coding https://t.co/JkA5iStofZ

The status 1266735261012111360 is posted by geeksforgeeks
This status says : 

With the access to our Job Portal, find the jobs that are best for you & experience happy placement journey....
.
L… https://t.co/mzMMFVzjMv

The status 1266342841648898049 is posted by geeksforgeeks
This status says : 

My reaction to this Lockdown : 

"Der Lagi Lekin... Maine Ab Hai Jeena Seekh Liya" 

What's your reaction to it?
.… https://t.co/nH9L0eewSr

```

**示例 2:** 使用带有 trim_user 参数的`statuses_lookup()`方法。

```
# list of status IDs to be fetched 
id_ = [1266978261701210112, 1266735261012111360, 1266342841648898049]

# fetching the statuses
statuses = api.statuses_lookup(id_, trim_user = True)

# printing the statuses
for status in statuses:
    print(status.user.id)
```

**输出:**

```
57741058
57741058
57741058

```