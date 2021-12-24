# 如何用 Python 从 YouTube Playlist 中提取图像信息？

> 原文:[https://www . geeksforgeeks . org/如何从 youtube 中提取图像信息-播放列表-使用-python/](https://www.geeksforgeeks.org/how-to-extract-image-information-from-youtube-playlist-using-python/)

**先决条件:** [YouTube API](https://www.geeksforgeeks.org/youtube-data-api-set-1/)

谷歌提供了一大套 API 供开发者选择。谷歌提供的每一项服务都有相关的应用编程接口。作为其中的一员，YouTube 数据应用编程接口使用起来非常简单，提供了如下功能

*   搜索视频
*   处理视频，如检索视频信息、插入视频、删除视频等。
*   处理订阅，如列出所有订阅，插入或删除订阅。
*   检索有关注释的信息，如对 parentid 标识的特定注释的回复等。

在本文中，我们将学习如何使用 Python 从 YouTube 播放列表中提取单个视频的图像信息

**我们将获取的图像信息:**

*   URL 图像
*   图像宽度和高度
*   不同尺寸的图像

**在 YouTube 视频中，有五种不同的缩略图，分别是:**

*   系统默认值
*   高的
*   madres
*   媒介
*   标准

**进场:**

*   我们将使用**构建**、**列表**、**执行**方法，它将给出播放列表详细信息
*   在列表方法中，在部分属性中传递**内容详细信息**，在**播放列表中传递**属性**播放列表中的**或**播放列表中的**
*   在**最大结果**和**页面令牌**中传递 50 值，最初传递**无**值

## 蟒蛇 3

```
nextPageToken=None

# creating youtube resource object 
youtube = build('youtube','v3',developerKey='Enter API Key')

while True:

  # retrieve youtube video results 
  pl_request = youtube.playlistItems().list(
    part='snippet',
    playlistId=playlistId.get(),
    maxResults=50,
    pageToken=nextPageToken
  )
  pl_response = pl_request.execute()

  nextPageToken = pl_response.get('nextPageToken')

  if not nextPageToken:
    break
```

*   遍历所有响应并获取图像信息

**下面是实现:**

## 蟒蛇 3

```
# import module
from googleapiclient.discovery import build

def playlist_video_links(playlistId):

    nextPageToken=None

    # creating youtube resource object 
    youtube = build('youtube','v3',developerKey='Enter API Key')

    while True:

        # retrieve youtube video results 
        pl_request = youtube.playlistItems().list(
            part='snippet',
            playlistId=playlistId,
            maxResults=50,
            pageToken=nextPageToken
            )
        pl_response = pl_request.execute()

        # Iterate through all response and fetch Image Information
        for item in pl_response['items']:

            thumbnails = item['snippet']['thumbnails']

            if 'default' in thumbnails:
                default = thumbnails['default']
                print(default)

            if 'high' in thumbnails:
                high = thumbnails['high']
                print(high)

            if 'maxres' in thumbnails:
                maxres = thumbnails['maxres']
                print(maxres)

            if 'medium' in thumbnails:
                medium = thumbnails['medium']
                print(medium)

            if 'standard' in thumbnails:
                standard = thumbnails['standard']
                print(standard)
            print("\n")

        nextPageToken = pl_response.get('nextPageToken')

        if not nextPageToken:
            break

playlist_video_links('PLsyeobzWxl7r2ukVgTqIQcl-1T0C2mzau')
```

**输出:**

<video class="wp-video-shortcode" id="video-551760-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210130100225/FreeOnlineScreenRecorderProject3.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210130100225/FreeOnlineScreenRecorderProject3.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210130100225/FreeOnlineScreenRecorderProject3.mp4)</video>