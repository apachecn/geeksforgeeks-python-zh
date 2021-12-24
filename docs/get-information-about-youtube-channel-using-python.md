# 使用 Python 获取 YouTube 频道的信息

> 原文:[https://www . geesforgeks . org/get-information-about-YouTube-channel-using-python/](https://www.geeksforgeeks.org/get-information-about-youtube-channel-using-python/)

**先决条件:** [YouTube API](https://www.geeksforgeeks.org/youtube-data-api-set-1/)

谷歌提供了一大套 API 供开发者选择。谷歌提供的每一项服务都有相关的应用编程接口。作为其中的一员，YouTube 数据应用编程接口使用起来非常简单，提供了如下功能

*   搜索视频
*   处理视频，如检索视频信息、插入视频、删除视频等。
*   处理订阅，如列出所有订阅，插入或删除订阅。
*   检索关于评论的信息，如对由**父标识**等标识的特定评论的回复。

在本文中，我们将使用 YouTube 应用编程接口在 Python 中执行各种 YouTube 操作。

## 获取 YouTube 频道信息

在本节中，我们将编写一个 python 脚本，该脚本将使用 Python 提取 YouTube 频道信息。

**频道信息:**

*   订户总数
*   视频总数
*   总视图

**进场:**

*   这里我们将使用 **build()** 、**channel()**、 **list()** 、 **execute()** 方法它将给出 YouTube 频道的详细信息。
*   在列表方式中，通过统计部分属性和 YouTube 频道的 **id** 属性通过 **channelId** 。

**下面是实现:**

## 蟒蛇 3

```py
# Import Module
from googleapiclient.discovery import build

# Create YouTube Object
youtube = build('youtube', 'v3',
                developerKey='Enter API key')

ch_request = youtube.channels().list(
    part='statistics',
    id='Enter Channel ID')

# Channel Information
ch_response = ch_request.execute()

sub = ch_response['items'][0]['statistics']['subscriberCount']
vid = ch_response['items'][0]['statistics']['videoCount']
views = ch_response['items'][0]['statistics']['viewCount']

print("Total Subscriber:- ", sub)
print("Total Number of Videos:- ", vid)
print("Total Views:- ", views)
```

**输出:**

<video class="wp-video-shortcode" id="video-552305-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210202172849/FreeOnlineScreenRecorderProject4.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210202172849/FreeOnlineScreenRecorderProject4.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210202172849/FreeOnlineScreenRecorderProject4.mp4)</video>

## 从 YouTube 播放列表中获取单个视频的描述

在本节中，我们将学习如何使用 Python 从 YouTube 播放列表中获取单个视频的描述。

**进场:**

*   我们将使用**构建**、**列表**、**执行**方法，它将给出播放列表详细信息。
*   在列表方法中，在部分属性中传递**片段**，在**播放列表中传递**属性**播放列表**或**播放列表**。
*   在**最大结果**和**页面标记**中传递 50 个值，最初不传递任何值。

**下面是实现:**

## 蟒蛇 3

```py
# Import Module
from googleapiclient.discovery import build

def playlist_video_links(playlistId):

    nextPageToken = None

    # Creating youtube resource object
    youtube = build('youtube', 'v3',
                    developerKey='Enter API Key')

    while True:

        # Retrieve youtube video results
        pl_request = youtube.playlistItems().list(
            part='snippet',
            playlistId=playlistId,
            maxResults=50,
            pageToken=nextPageToken
        )
        pl_response = pl_request.execute()

        # Iterate through all response and get video description
        for item in pl_response['items']:

            description = item['snippet']['description']

            print(description)

            print("\n")

        nextPageToken = pl_response.get('nextPageToken')

        if not nextPageToken:
            break

playlist_video_links('Enter Playlist ID')
```

**输出:**

<video class="wp-video-shortcode" id="video-552305-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210131111038/FreeOnlineScreenRecorderProject2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210131111038/FreeOnlineScreenRecorderProject2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210131111038/FreeOnlineScreenRecorderProject2.mp4)</video>

## 统计 YouTube 频道的播放列表数量

在本节中，我们将编写一个 Python 脚本，它将使用 YouTube 应用编程接口计算 YouTube 频道播放列表的数量。

**进场:**

*   这里我们将使用 **build()** 、**playlist()**、 **list()** 、 **execute()** 方法它将给出 YouTube 频道的详细信息。
*   在**列表**方法中，传递**内容详细信息**和**片段**在部分属性和**通道化**属性中传递**通道化**。

**下面是实现:**

## 蟒蛇 3

```py
# Import Module
from googleapiclient.discovery import build

# Create YouTube Object
youtube = build('youtube', 'v3',
                developerKey='Enter API key')

# Get video count
def Channel_Depth_details(channel_id):
    pl_request = youtube.playlists().list(
        part='contentDetails,snippet',
        channelId='channel_id',
        maxResults=50
    )
    pl_response = pl_request.execute()

    return len(pl_response['items'])

print(Channel_Depth_details("Channel ID"))
```

**输出:**

<video class="wp-video-shortcode" id="video-552305-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210202174022/FreeOnlineScreenRecorderProject5.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20210202174022/FreeOnlineScreenRecorderProject5.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210202174022/FreeOnlineScreenRecorderProject5.mp4)</video>