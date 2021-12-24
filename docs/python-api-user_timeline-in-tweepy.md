# Python–API . user _ timeline()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-user _ timeline-in-tweepy/](https://www.geeksforgeeks.org/python-api-user_timeline-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.user_timeline()

Tweepy 模块中`API`类的 **`user_timeline()`** 方法用于获取认证用户或指定用户发布的 20 个最新状态。

> **语法:** API.user_timeline(参数)
> 
> **参数:**
> 
> *   **id :** 指定用户的 id 或屏幕名称。
> *   **user_id :** 指定用户的 id，当有效的用户 ID 也是有效的屏幕名称时，用于区分帐户。
> *   **screen_name :** 指定用户的屏幕名称，当有效的屏幕名称也是用户 id 时，用于区分帐户。
> *   **自 _ 号:**只获取比指定号更新的状态。
> *   **最大标识:**仅获取早于或等于指定标识的状态。
> *   **计数:**待取状态数，默认值为 20。
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

# screen name of the account to be fetched
screen_name = "geeksforgeeks"

# fetching the statuses
statuses = api.user_timeline(screen_name)

print(str(len(statuses)) + " number of statuses have been fetched.")
```

**输出:**

```
20 number of statuses have been fetched.

```

**示例 2:** 使用带有计数参数的`user_timeline()`方法仅获取指定数量的状态。

```
# screen name of the account to be fetched
screen_name = "geeksforgeeks"

# number of statuses to be fetched
count = 3

# fetching the statuses
statuses = api.user_timeline(screen_name, count = count)

# printing the statuses
for status in statuses:
    print(status.text, end = "\n\n")
```

**输出:**

```
Hola Geeks!
.
Tell us what did you learned during this lockdown?
.
#MondayMotivation #mondaythoughts #codinglife… https://t.co/1mVLOKdaIL

@ZomatoIN Avoid Errors, not Client calls
#sundayvibes #programmingmemes

Avoid errors, not client calls
.
Geeks, Keep this going...
.
#sundayvibes #programming #programmingmemes #coding https://t.co/JkA5iStofZ

```