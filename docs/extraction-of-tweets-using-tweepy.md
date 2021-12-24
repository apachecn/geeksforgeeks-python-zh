# 使用 Tweepy 提取推文

> 原文:[https://www . geeksforgeeks . org/extraction-of-tweepy-using/](https://www.geeksforgeeks.org/extraction-of-tweets-using-tweepy/)

**简介:** Twitter 是一个受欢迎的社交网络，用户在这里分享被称为推文的消息。Twitter 允许我们使用 Twitter API 或 Tweepy 来挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

**获取密钥的步骤:**
–登录推特开发者区
–转到“创建应用”
–填写应用的详细信息。
–点击创建您的推特应用程序
–您的新应用程序的详细信息将与消费者密钥和消费者秘密一起显示。
–对于访问令牌，单击“创建我的访问令牌”。该页面将刷新并生成访问令牌。

Tweepy 是应该使用 pip 安装的库之一。现在，为了授权我们的应用程序代表我们访问推特，我们需要使用 OAuth 接口。Tweepy 提供了方便的游标接口来迭代不同类型的对象。Twitter 最多允许提取 3200 条推文。

这些都是获取用户推文之前必须使用的前提条件。

**代码(附说明):**

```
import tweepy

# Fill the X's with the credentials obtained by 
# following the above mentioned procedure.
consumer_key = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" 
consumer_secret = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"
access_key = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"
access_secret = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"

# Function to extract tweets
def get_tweets(username):

        # Authorization to consumer key and consumer secret
        auth = tweepy.OAuthHandler(consumer_key, consumer_secret)

        # Access to user's access key and access secret
        auth.set_access_token(access_key, access_secret)

        # Calling api
        api = tweepy.API(auth)

        # 200 tweets to be extracted
        number_of_tweets=200
        tweets = api.user_timeline(screen_name=username)

        # Empty Array
        tmp=[] 

        # create array of tweet information: username, 
        # tweet id, date/time, text
        tweets_for_csv = [tweet.text for tweet in tweets] # CSV file created 
        for j in tweets_for_csv:

            # Appending tweets to the empty array tmp
            tmp.append(j) 

        # Printing the tweets
        print(tmp)

# Driver code
if __name__ == '__main__':

    # Here goes the twitter handle for the user
    # whose tweets are to be extracted.
    get_tweets("twitter-handle") 
```

**结论:**
上面的脚本将生成特定用户的所有推文，并将其附加到空数组 tmp 中。在这里，Tweepy 是作为一种工具引入的，它可以用 Python 以相当简单的方式访问推特数据。我们可以收集不同类型的数据，明显的重点是“推文”对象。一旦我们收集了一些数据，分析应用的可能性就无穷无尽了。

提取推文的一个这样的应用是情绪或情感分析。用户的情绪可以通过标记每个单词并对该数据应用机器学习算法来从推文中获得。这种情感或情绪检测在世界范围内使用，并将在未来得到广泛应用。

本文由 **Ayush Govil** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。