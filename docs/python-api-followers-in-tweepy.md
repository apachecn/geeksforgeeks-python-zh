# Tweepy

中的 Python–API . followers()

> 原文:[https://www . geesforgeks . org/python-API-followers-in-tweepy/](https://www.geeksforgeeks.org/python-api-followers-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.followers()

Tweepy 模块中`API`类的 **`followers()`** 方法用于获取指定用户的关注者，这些关注者是在其中添加的。

> **语法:**API . followers(id/user _ id/screen _ name)
> 
> **参数:**仅使用 3 个选项之一:
> **id :** 指定用户的 id 或屏幕名称
> **user_id :** 指定用户的 id，当有效的用户 ID 也是有效的屏幕名称时对区分账户有用
> **screen_name :** 指定用户的屏幕名称，当有效的屏幕名称也是用户 ID 时对区分账户有用
> 
> **返回:**用户类的对象列表

**示例 1:**followers()方法返回最近的 20 个 followers。

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

# the screen_name of the targeted user
screen_name = "geeksforgeeks"

# printing the latest 20 followers of the user
for follower in api.followers(screen_name):
    print(follower.screen_name)
```

**输出:**

```
ManojChevula
davidasem_
rajneesosho
sl_jens
Sandeep06081
abdulwhabalras2
chryptografio
_Mohit_Rajput_
elamineyamani
abhiSharma0311
PawanYa87321156
yagneshmb
yogeekabhi
DarioGallardo2
imharsan
MOHAMMA18757894
ArunKum79855492
ans_human_ap
1nonlyabhi

```

**示例 2:** 使用`Cursor()`方法可以访问超过 20 个关注者。

```
# the screen_name of the targeted user
screen_name = "geeksforgeeks"

# getting only 30 followers
for follower in tweepy.Cursor(api.followers, screen_name).items(30):
    print(follower.screen_name)
```

**输出:**

```
mr_manav852
MohsinI09002010
educatorly
JimXu_artist
JaiHin303
Indrajeet307
sainisajal147
aryangarg22
Ashutos11691851
ManojChevula
davidasem_
osho957
sl_jens
Sandeep06081
abdulwhabalras2
chryptografio
_Mohit_Rajput_
elamineyamani
abhiSharma0311
PawanYa87321156
yagneshmb
yogeekabhi
DarioGallardo2
imharsan
MOHAMMA18757894
ArunKum79855492
ans_human_ap
1nonlyabhi
SimplicitySol2
prateekmaj21

```

**例 3:** 统计跟随者数量。

```
# the screen_name of the targeted user
screen_name = "geeksforgeeks"

# getting all the followers
c = tweepy.Cursor(api.followers, screen_name)

# counting the number of followers
count = 0
for follower in c.items():
    count += 1
print(screen_name + " has " + str(count) + " followers.")
```

**输出:**

```
geeksforgeeks has 17338 followers.
```