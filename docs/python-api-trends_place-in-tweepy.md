# Python–API . trends _ place()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-trends _ place-in-tweepy/](https://www.geeksforgeeks.org/python-api-trends_place-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.trends_place()

Tweepy 模块中`API`类的 **`trends_place()`** 方法用于获取特定位置的前 50 个趋势主题。

> **语法:** API.trends_place(id，exclude)
> 
> **参数:**
> 
> *   **id :** Yahoo！地点的地球标识
> *   **排除:**将此参数设置为“哈希表”时，会从列表中排除哈希表。
> 
> **返回:【JSON 类的一个对象**

**例 1 :**

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

# WOEID of London
woeid = 44418

# fetching the trends
trends = api.trends_place(id = woeid)

# printing the information
print("The top trends for the location are :")

for value in trends:
    for trend in value['trends']:
        print(trend['name'])
```

**输出:**

```py
The top trends for the location are :
Little Britain
#theAword
Peter Shilton
#AHouseThroughTime
Michael O'Neill
#Gclash10
Gladstone
Shilts
White Chicks
Robert Milligan
#GeorgeFloydFuneral
#RhodesMustFall
Prince Philip
Wretch 32
Tower Hamlets
Seyi
Auschwitz
Fact 4
Persona 4 Golden
Matt Lucas
Eddie Murphy
Love Thy Neighbour
Paul Walker
Lord Sainsbury
Fawlty Towers
Peter Hitchens
Chester Zoo
Bogus Journey
Afua
The Hour Of Bewilderbeast
Gareth Southgate
hand of god
#whowantstobeamillionaire
#StupidZoomQuestions
#dailybriefings
#VogueChallenge
#HolbyCity
#SBSwinnershour
#craftbeerhour
#GHB2B
#DontFilterFeelings
#OURfPBookBlether
#GBBO
#landofthemidnightsun
#UnlockingTheNHS
#ShutDownSTEM
#UFC251
#SaveOurZoos
#TWUG
#DisneySongOrBand

```

**示例 2 :** 使用参数 exclude。

```py
# WOEID of New York
woeid = 2459115

# fetching the trends
trends = api.trends_place(id = woeid, exclude = "hashtags")

# printing the information
print("The top trends for the location are :")

for value in trends:
    for trend in value['trends']:
        print(trend['name'])
```

**输出:**

```py
The top trends for the location are :
Molly
Lakers
Kobe
McDonald
Lawrence
B Simone
Stephen Miller
Henry Winkler
Persona 4 Golden
Mike O'Meara
Kemp
RATM
Stassi
Dick Johnson
Pat Lynch
Chad Daybell
Fulton County
Stan Lee
Neyo
Capitol Hill Autonomous Zone
jax and brittany
Chester Bennington
General Brown
The Batman
James Demarco
Respect is EARNED
Voting Rights Act
Better MC
My 9-5
Ryan Garcia
Denuvo
Congratulations Yamiche

```