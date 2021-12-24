# 使用 Python 提取包含特定标签的推文

> 原文:[https://www . geesforgeks . org/extracting-tweets-包含-特定-hashtag-use-python/](https://www.geeksforgeeks.org/extracting-tweets-containing-a-particular-hashtag-using-python/)

推特是最受欢迎的社交媒体平台之一。推特应用编程接口提供了你需要的工具来参与、参与和分析发生在推特上的对话，这在数据分析和人工智能等领域有很多应用。本文主要讨论如何从给定日期开始提取具有特定标签的推文。

### 要求:

*   **Tweepy** 是一个 Python 包，旨在方便访问推特应用编程接口。推特应用编程接口提供的几乎所有功能都可以通过 *Tweepy* 使用。要安装此软件，请在终端中键入以下命令。

```py
pip install Tweepy

```

*   **Pandas** 是 python 中非常强大的数据分析框架。它建立在 *Numpy* 包上，其关键数据结构是*数据框架*，用户可以在其中操作表格数据。要安装此软件，请在终端中键入以下命令。

```py
pip install pandas

```

### **先决条件:**

*   创建一个推特开发者账号，获取你的消费者密钥和访问令牌
*   通过在命令提示符下运行以下命令，在您的系统上安装 *Tweepy* 和 *Pandas* 模块

### 逐步方法:

1.  导入所需模块。
2.  创建一个显式函数来显示推文数据。
3.  使用 *tweepy* 模块创建另一个函数来抓取给定标签的数据。
4.  在驱动程序代码中，分配推特开发者帐户凭证以及标签、初始日期和推文数量。
5.  最后，调用函数以 Hashtag、初始日期和推文数量作为参数来抓取数据。

**以下是基于上述方法的完整程序:**

## 蟒蛇

```py
# Python Script to Extract tweets of a 
# particular Hashtag using Tweepy and Pandas

# import modules
import pandas as pd
import tweepy

# function to display data of each tweet
def printtweetdata(n, ith_tweet):
    print()
    print(f"Tweet {n}:")
    print(f"Username:{ith_tweet[0]}")
    print(f"Description:{ith_tweet[1]}")
    print(f"Location:{ith_tweet[2]}")
    print(f"Following Count:{ith_tweet[3]}")
    print(f"Follower Count:{ith_tweet[4]}")
    print(f"Total Tweets:{ith_tweet[5]}")
    print(f"Retweet Count:{ith_tweet[6]}")
    print(f"Tweet Text:{ith_tweet[7]}")
    print(f"Hashtags Used:{ith_tweet[8]}")

# function to perform data extraction
def scrape(words, date_since, numtweet):

    # Creating DataFrame using pandas
    db = pd.DataFrame(columns=['username', 'description', 'location', 'following',
                               'followers', 'totaltweets', 'retweetcount', 'text', 'hashtags'])

    # We are using .Cursor() to search through twitter for the required tweets.
    # The number of tweets can be restricted using .items(number of tweets)
    tweets = tweepy.Cursor(api.search, q=words, lang="en",
                           since=date_since, tweet_mode='extended').items(numtweet)

    # .Cursor() returns an iterable object. Each item in 
    # the iterator has various attributes that you can access to 
    # get information about each tweet
    list_tweets = [tweet for tweet in tweets]

    # Counter to maintain Tweet Count
    i = 1  

    # we will iterate over each tweet in the list for extracting information about each tweet
    for tweet in list_tweets:
        username = tweet.user.screen_name
        description = tweet.user.description
        location = tweet.user.location
        following = tweet.user.friends_count
        followers = tweet.user.followers_count
        totaltweets = tweet.user.statuses_count
        retweetcount = tweet.retweet_count
        hashtags = tweet.entities['hashtags']

        # Retweets can be distinguished by a retweeted_status attribute,
        # in case it is an invalid reference, except block will be executed
        try:
            text = tweet.retweeted_status.full_text
        except AttributeError:
            text = tweet.full_text
        hashtext = list()
        for j in range(0, len(hashtags)):
            hashtext.append(hashtags[j]['text'])

        # Here we are appending all the extracted information in the DataFrame
        ith_tweet = [username, description, location, following,
                     followers, totaltweets, retweetcount, text, hashtext]
        db.loc[len(db)] = ith_tweet

        # Function call to print tweet data on screen
        printtweetdata(i, ith_tweet)
        i = i+1
    filename = 'scraped_tweets.csv'

    # we will save our database as a CSV file.
    db.to_csv(filename)

if __name__ == '__main__':

    # Enter your own credentials obtained 
    # from your developer account
    consumer_key = "XXXXXXXXXXXXXXXXXXXXX"
    consumer_secret = "XXXXXXXXXXXXXXXXXXXXX"
    access_key = "XXXXXXXXXXXXXXXXXXXXX"
    access_secret = "XXXXXXXXXXXXXXXXXXXXX"
    auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
    auth.set_access_token(access_key, access_secret)
    api = tweepy.API(auth)

    # Enter Hashtag and initial date
    print("Enter Twitter HashTag to search for")
    words = input()
    print("Enter Date since The Tweets are required in yyyy-mm--dd")
    date_since = input()

    # number of tweets you want to extract in one run
    numtweet = 100  
    scrape(words, date_since, numtweet)
    print('Scraping has completed!')
```