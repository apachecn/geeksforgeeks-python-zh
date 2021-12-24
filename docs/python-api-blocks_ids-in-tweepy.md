# Python–Tweepy

中的 API.blocks_ids()

> 原文:[https://www . geesforgeks . org/python-API-blocks _ ids-in-tweepy/](https://www.geeksforgeeks.org/python-api-blocks_ids-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.blocks _ ids()

Tweepy 模块中`API`类的 **`blocks_ids()`** 方法用于获取被认证用户阻止的用户的所有用户 id 列表。

> **语法:** API.blocks_ids()
> 
> **参数:**无
> 
> **返回:**整数列表

**示例 1 :** 使用`blocks_ids()`方法查找被认证用户阻止的用户数量。

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
blocked_users = api.blocks_ids()

# printing the number of blocked users
print(len(blocked_users))
```

**输出:**

```py
63
```

**示例 2 :** 使用`blocks_ids()`方法查找被认证用户阻止的所有用户的用户标识。

```py
# getting the blocked users
blocked_users = api.blocks_ids()

# printing the user IDs of the blocked users
for IDs in blocked_users:
    print(IDs)
```

**输出:**

```py
28406270
292558545
705807268835672064
65851020
1246402093851856896
1492538024
323599188
130557513
1082334352711790593
167272426
101311381
147994804
419107960
256999501
108577950
1432374242
715401445785210880
1187330941
46062566
236826818
706044393749417984
1120868702298066945
90346496
16485058
4316769252
3242292793
594785338
68399705
189917061
1130956814567260161
990908549768200192
900223598144757763
963800904540540928
2289518994
922564729
3220084519
952841063273709568
16948493
380749300
841712647246614531
3305945622
101494182
129731515
784682859286130689
132385468
2583217418
2455275793
762299610765271040
772180779640033281
826117446050381826
2097571
826091183491387394
826099053788327936
338444460
232193350
392608775
891250296512323585
2247560024
2835317718
804006430063759360
2982269822
792319459759386624
80876565

```