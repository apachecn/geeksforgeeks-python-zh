# Python–API . list _ subscribers()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-list _ subscribers-in-tweepy/](https://www.geeksforgeeks.org/python-api-list_subscribers-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.list_subscribers()

Tweepy 模块中 API 类的 **list_subscribers()** 方法用于获取指定列表的订阅者。

> **语法:** API.list_subscribers(参数)
> **参数:**
> 
> *   **列表 _id :** 列表的 id。
> *   **鼻涕虫:**列表中的鼻涕虫。
> *   **所有者 _id :** 列表所有者的 id。
> *   **所有者 _ 屏幕 _ 名称:**列表所有者的屏幕名称。
> *   **计数:**要获取的订户数。
> *   **skip _ States:**确定是否返回状态的布尔值。
> 
> **返回:**类用户的对象列表

**例 1 :** 打印最近 20 个订阅者的网名。

## 蟒蛇 3

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

# the slug of the list
slug = "thought-leaders"

# the screen name of the owner of the list
owner_screen_name = "kitson"

# fetching the subscribers
subscribers = api.list_subscribers(slug = slug,
                                   owner_screen_name = owner_screen_name)

# printing the screen names of the subscribers
for subscriber in subscribers:
    print(subscriber.screen_name)
```

**输出:**

```
Saddds305
rachellelive
hazemkhattab8
constantine_fry
rockivy4
edwinealmonte
satishvkvn
puppies221122
55_CancriF
jameschancepro1
LiptakCarl
TheMarkShaw
mitch_plzzzz
ahrimango
nidhishetty
jmpena33
TuttleRose
rgolwalkar
BillRingle
Nellie_I_Am
```

**示例 2 :** 使用 count 参数仅获取指定数量的订户。

## 蟒蛇 3

```
# the slug of the list
slug = "thought-leaders"

# the screen name of the owner of the list
owner_screen_name = "kitson"

# number of subscribers to be fetched
count = 3

# fetching the subscribers
subscribers = api.list_subscribers(slug = slug,
                                   owner_screen_name = owner_screen_name,
                                   count = count)

print("The number of subscriers fetched : " + str(len(subscribers)))
```

**输出:**

```
The number of subscriers fetched : 3
```