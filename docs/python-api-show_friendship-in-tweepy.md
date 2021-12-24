# Python–API . show _ friendly()in Tweepy

> 原文:[https://www . geesforgeks . org/python-API-show _ friendly-in-tweepy/](https://www.geeksforgeeks.org/python-api-show_friendship-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从推特开发者那里获得消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.show _ 友谊()

Tweepy 模块中 API 类的**show _ friendly()**方法用于获取两个用户之间的详细关系。

> **语法:**API . show _ friendly(source _ id/source _ screen _ name，target _ id/target _ screen _ name)
> **参数:**
> 
> *   **source_id :** 指定用户 1 的 id。
> *   **source_screen_name :** 指定用户 1 的屏幕名称。
> *   **target_id :** 指定用户 2 的 id。
> *   **target_screen_name :** 指定用户 2 的屏幕名称。
> 
> **返回:**友谊类的对象

**示例 1 :** 使用屏幕名称分析友谊。

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

# screen name of the account 1
source_screen_name = "Twitter"

# screen name of the account 2
target_screen_name = "TwitterIndia"

# getting the friendship details
friendship = api.show_friendship(source_screen_name = source_screen_name, target_screen_name = target_screen_name)

print("Is " + friendship[0].screen_name + " followed by " + friendship[1].screen_name, end = "? : ")
if friendship[0].followed_by == False:
    print("No")
else:
    print("Yes")

print("Is " + friendship[0].screen_name + " following " + friendship[1].screen_name, end = "? : ")
if friendship[0].following == False:
    print("No")
else:
    print("Yes")
```

**输出:**

```py
Is Twitter followed by TwitterIndia? : Yes
Is Twitter following TwitterIndia? : No
```

**示例 2 :** 使用用户标识分析友谊。

## 蟒蛇 3

```py
# user ID of the account 1
source_id = 14230524

# user ID of the account 2
target_id = 34507480

# getting the friendship details
friendship = api.show_friendship(source_id = source_id, target_id = target_id)

print("The screen name of user 1 is : " + friendship[0].screen_name)
print("The screen name of user 2 is : " + friendship[1].screen_name)

print("Is " + friendship[0].screen_name + " followed by " + friendship[1].screen_name, end = "? : ")
if friendship[0].followed_by == False:
    print("No")
else:
    print("Yes")

print("Is " + friendship[0].screen_name + " following " + friendship[1].screen_name, end = "? : ")
if friendship[0].following == False:
    print("No")
else:
    print("Yes")
```

**输出:**

```py
The screen name of user 1 is : ladygaga
The screen name of user 2 is : ArianaGrande
Is ladygaga followed by ArianaGrande? : Yes
Is ladygaga following ArianaGrande? : No
```