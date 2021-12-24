# Python–Tweepy 中的 API.blocks()

> 原文:[https://www.geeksforgeeks.org/python-api-blocks-in-tweepy/](https://www.geeksforgeeks.org/python-api-blocks-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.blocks()

Tweepy 模块中`API`类的 **`blocks()`** 方法用于获取被认证用户阻止的所有用户的列表。

> **语法:** API.blocks()
> 
> **参数:**无
> 
> **返回:**用户类的对象列表

**示例 1 :** 使用`blocks()`方法查找被认证用户阻止的用户数量。

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

# getting the blocked users
blocked_users = api.blocks()

# printing the number of blocked users
print(len(blocked_users))
```

**输出:**

```py
63
```

**示例 2 :** 使用`blocks()`方法查找被认证用户阻止的所有用户的屏幕名称。

```py
# getting the blocked users
blocked_users = api.blocks()

# printing the screen names of the blocked users
for user in blocked_users:
    print(user.screen_name)
```

**输出:**

```py
kumailn
NorbertElekes
fjamie013
Trendulkar
iShivamDubey
KapilSharmaK9
gaywonk
mehdirhasan
Ilhan
Begin_Humor
iamsrk
rishibagree
Turki_alalshikh
ahrefs
devduttmyth
Francesgracella
realshooterdadi
h3h3productions
indiantweeter
AdnanSamiLive
AjitKDoval_FAN
piyushpatriotic
TheSamirAbbas
sonalkalra
MsBlaireWhite
vishal_ketto
fay_alif
vivekoberoi
waglenikhil
AMMARlSE
AyushPa89314914
MSArenaOfficial
DilipVa37961599
sunilku31690409
ViratGang
narendramodi177
katrinakaif_4
tariqnasheed
Apple
HolyKaaba
AisiTaisiDemo
sanjivbhatt
saudipost
arifkhanesm
BeingSalmanKhan
AcharyaPramodk
iAnkurSingh
HinduDharma1
WakeUpHindu
bbcnewstelugu
cnni
bbcnewspunjabi
bbcnewsmarathi
AtheistRepublic
rajshah
Shehzad_Ind
siddaramaiah
FeminismInIndia
RVCJ_FB
MFSahiHai
TheQuint
BilalMadni13
AmbedkarCaravan

```