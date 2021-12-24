# Python–API . friends()在 Tweepy 中

> 原文:[https://www.geeksforgeeks.org/python-api-friends-in-tweepy/](https://www.geeksforgeeks.org/python-api-friends-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.friends()

Tweepy 模块中`API`类的 **`friends()`** 方法用于获取指定用户的好友(他们正在关注的用户)在其中添加的顺序。

> **语法:**API . friends(id/user _ id/screen _ name)
> 
> **参数:**仅使用 3 个选项中的一个:
> **id :** 指定用户的 id 或屏幕名称
> **user_id :** 指定用户的 id，当有效用户 ID 也是有效屏幕名称时用于区分账户
> **screen_name :** 指定用户的屏幕名称，当有效屏幕名称也是用户 ID 时用于区分账户
> 如果没有指定用户，则默认为认证用户。
> 
> **返回:**用户类的对象列表

**示例 1:**friends()方法返回最近的 20 个朋友。

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
screen_name = "TwitterIndia"

# printing the latest 20 friends of the user
for friend in api.friends(screen_name):
    print(friend.screen_name)
```

**输出:**

```
misskaul
rajyasabhatv
DDNewslive
TwitterMedia
abpmajhatv
htTweets
News18Haryana
jack
BBCHindi
the_hindu
mentalhealthind
ProKabaddi
firstpost
livemint
hcmariwala
mathrubhumi
PTUshaOfficial
anubhabhonsle
kmmalleswari
DipaKarmakar

```

**例 2:** 使用`Cursor()`方法可以访问 20 多个好友。

```
# the screen_name of the targeted user
screen_name = "TwitterIndia"

# getting only 30 friends
for friend in tweepy.Cursor(api.friends, screen_name).items(30):
    print(friend.screen_name)
```

**输出:**

```
misskaul
rajyasabhatv
DDNewslive
TwitterMedia
abpmajhatv
htTweets
News18Haryana
jack
BBCHindi
the_hindu
mentalhealthind
ProKabaddi
firstpost
livemint
hcmariwala
mathrubhumi
PTUshaOfficial
anubhabhonsle
kmmalleswari
DipaKarmakar
NewIndianXpress
M_Raj03
DDNational
isro
PTTVOnlineNews
cricketnext
thebetterindia
AGSawant
MahendraP_BJP
DrRPNishank

```

**例 3:** 统计跟随者数量。

```
# the screen_name of the targeted user
screen_name = "geeksforgeeks"

# getting all the friends
c = tweepy.Cursor(api.friends, screen_name)

# counting the number of friends
count = 0
for friends in c.items():
    count += 1
print(screen_name + " has " + str(count) + " friends.")
```

**输出:**

```
geeksforgeeks has 8 friends.
```