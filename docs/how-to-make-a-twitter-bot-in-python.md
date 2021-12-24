# 如何用 Python 制作推特 Bot？

> 原文:[https://www . geesforgeks . org/how-to-make-a-Twitter-bot-in-python/](https://www.geeksforgeeks.org/how-to-make-a-twitter-bot-in-python/)

推特是一项美国微博和社交网络服务，用户可以在上面发布被称为“**推文**”的消息并与之互动。在本文中，我们将使用 Python 制作一个**推特机器人。**

Python 和 Javascript 都可以用来开发一个**自动推特机器人**，它可以自己完成很多任务，比如:

*   **Forward the tweet of specific **# hastags** .**
***   **Favorite/like** tweets with specific **# tags** .*   **Users who tweet with** specific **# tag** .*   If permission is obtained, user can also be DM at **.****

## **要求**

### **安装 Tweepy**

**为此，我们需要一个名为**Twepy**的 Python 库来访问**推特应用编程接口**。我们可以通过三种方式安装 tweepy:**

****1。使用 pip 命令****

```
$ pip install tweepy 
```

****2。克隆 tweepy****

```
$ git clone https://github.com/tweepy/tweepy.git
$ cd tweepy
$ pip install 
```

**的 GitHub 存储库

**3。直接克隆仓库**T0

### 注册推特开发者账号

*   为你的推特机器人注册一个单独的账户，然后通过这个链接申请推特开发者账户[https://developer.twitter.com/en/apply-for-access](https://developer.twitter.com/en/apply-for-access)
*   输入必要的详细信息，等待您的邮件确认。确认后，点击**创建应用程序**选项。
*   输入生成**密钥和访问令牌**所需的详细信息。
*   复制钥匙并保证它们的安全。

## 开发推特机器人

制作文件 ***推特 bot_retweet.py*** 并粘贴以下代码。

## 蟒 3

```
import tweepy
from time import sleep
from credentials import * 
from config import QUERY, FOLLOW, LIKE, SLEEP_TIME

auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)
api = tweepy.API(auth)

print("Twitter bot which retweets, like tweets and follow users")
print("Bot Settings")
print("Like Tweets :", LIKE)
print("Follow users :", FOLLOW)

for tweet in tweepy.Cursor(api.search, q = QUERY).items():
    try:
        print('\nTweet by: @' + tweet.user.screen_name)

        tweet.retweet()
        print('Retweeted the tweet')

        # Favorite the tweet
        if LIKE:
            tweet.favorite()
            print('Favorited the tweet')

        # Follow the user who tweeted
        # check that bot is not already following the user
        if FOLLOW:
            if not tweet.user.following:
                tweet.user.follow()
                print('Followed the user')

        sleep(SLEEP_TIME)

    except tweepy.TweepError as e:
        print(e.reason)

    except StopIteration:
        break
```

现在制作另一个文件来指定你的机器人应该做什么。命名为*T1T3】*

根据您的选择等编辑****#标签**，或者选择**真或假**。**

 **## 蟒 3

```
# Edit this config.py file as you like

# This is hastag which Twitter bot will
# search and retweet You can edit this with
# any hastag .For example : '# javascript'

QUERY = '# anything'

# Twitter bot setting for liking Tweets
LIKE = True

# Twitter bot setting for following user who tweeted
FOLLOW = True

# Twitter bot sleep time settings in seconds. 
# For example SLEEP_TIME = 300 means 5 minutes.
# Please, use large delay if you are running bot 
# all the time so that your account does not
# get banned.

SLEEP_TIME = 300
```** 

**接下来创建一个文件 ***凭证. py*** 并小心地将您的访问令牌粘贴在单引号“”之间。**

 **## 蟒 3

```
# This is just a sample file. You need to
# edit this file. You need to get these
# details from your Twitter app settings.

consumer_key = ''
consumer_secret = ''
access_token = ''
access_token_secret = ''
```** 

## **部署**

**使用此命令从命令提示符/终端运行**twitertbot _ retweet . py**文件。**

```
$ python twitterbot_retweet.py 
```

****而且管用！！******