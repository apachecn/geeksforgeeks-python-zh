# Python–API . Favorites()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-favorites-in-tweepy/](https://www.geeksforgeeks.org/python-api-favorites-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API .收藏夹()

Tweepy 模块中`API`类的 **`favorites()`** 方法用于获取用户的喜欢状态，一次 20 个。

> **语法:** API .收藏夹(id / user_id / screen_name)
> 
> **参数:**仅使用 3 个选项之一:
> 
> *   **id :** 指定用户的 id 或屏幕名称。
> *   **user_id :** 指定用户的 id，当有效的用户 ID 也是有效的屏幕名称时，用于区分帐户。
> *   **screen_name :** 指定用户的屏幕名称，当有效的屏幕名称也是用户 id 时，用于区分帐户。
> 
> **返回:**类状态的对象列表

**示例 1 :** 使用不带任何参数的`favorites()`方法返回认证用户的喜欢状态。

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

# getting the liked statuses
favorites = api.favorites()

# printing the screen names of the status posters
for status in favorites:
    print(status.user.screen_name)
```

**输出:**

```
oldschoolmonk
notcapnamerica
sardesairajdeep
Artie_Pavlov
BabitaPhogat
notcapnamerica
DerekGreaser
MarkDice
AOC
notcapnamerica
coolfunnytshirt
AOC
CNMparody
marwilliamson
YourAnonCentral
SanjeevSanskrit
4TheCulture____
tify330
AOC
matthewferner

```

**例 2 :** 使用参数屏幕名称为`favorites()`的方法。

```
# screen name of the user
screen_name = "geeksforgeeks"

# getting the liked statuses
favorites = api.favorites(screen_name)

# printing the screen names of the status posters
for status in favorites:
    print(status.user.screen_name)
```

**输出:**

```
abhinav26925233
adieti_sharma
vc90
KasatNiraj
harshitabambure
vc90
dns4u
bhagat_dinesh
BafnaTweets
malgattirajat
adieti_sharma
c_deep07
Its_username_yo
Rituraj97082167
Martial_Coder
baniya_buddy_
burgerNpizza
YehTuneKyaKiya
tweetsbybabua
shivankgtm

```