# Python–API . lookup _ friends()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-lookup _ friends-in-tweepy/](https://www.geeksforgeeks.org/python-api-lookup_friendships-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.lookup _ friendships()

Tweepy 模块中`API`类的 **`lookup_friendships()`** 方法用于获取认证用户和用户列表之间的详细关系，一次最多 100 个。

> **语法:**API . lookup _ friends(用户名/屏幕名)
> 
> **参数:**仅使用两个选项之一:
> 
> *   **用户标识:**指定用户标识的列表。
> *   **屏幕名称:**指定用户屏幕名称的列表。
> 
> **返回:**类关系的一个对象

**示例 1 :** 使用屏幕名称分析关系。

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

# list of screen names
screen_names = ["SrBachchan",
                "akshaykumar",
                "imVkohli",
                "sachin_rt",
                "SonuSood"]

# getting the friendship details
friendships = api.lookup_friendships(screen_names = screen_names)

for friendship in friendships:
    print("Is the authenticated user following " + friendship.screen_name, end = "? : ")
    print(friendship.is_following)
```

**输出:**

```py
Is the authenticated user following SrBachchan? : False
Is the authenticated user following akshaykumar? : True
Is the authenticated user following imVkohli? : True
Is the authenticated user following sachin_rt? : False
Is the authenticated user following SonuSood? : False

```

**示例 2 :** 使用用户标识分析关系。

```py
# list of user IDs
user_ids = [813286,
            27260086,
            21447363,
            79293791,
            17919972]

# getting the friendship details
friendships = api.lookup_friendships(user_ids = user_ids)

for friendship in friendships:
    print("Is the authenticated user following " + friendship.screen_name, end = "? : ")
    print(friendship.is_following)
```

**输出:**

```py
Is the authenticated user following BarackObama? : True
Is the authenticated user following justinbieber? : False
Is the authenticated user following katyperry? : False
Is the authenticated user following rihanna? : False
Is the authenticated user following taylorswift13? : False

```